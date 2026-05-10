---
title: "vlakna1.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/prednasky/vlakna1.txt"
date: 2009-02-19
type: TXT
---

Linux a vlákna 
Vladimír Michl, 7. srpna 1998 

Tento èlánek si klade za úkol seznámit ètenáøe s vlákny v Linuxu a jejich pouitím, pøípadnì s tím, èeho by se mìl èlovìk pøi pouívání vláken vyvarovat. 

Ale od zaèátku. Nejprve je tøeba osvìtlit rozdíl mezi termínem proces a vlákno. 

Jako proces je v systému chápán souhrn kódu programu, dat programu, zásobníku, údajù o procesem otevøenıch souborech, a také informací ohlednì zpracování signálù. Tyto všechny informace má kadı proces vlastní (privátní) a nemùe je sdílet s jinım procesem, kromì datovıch oblastí. Pøi volání jádra fork(2) se pak tyto informace pro novı proces skopírují, take jsou pro nìj zase privátní. 

Jako vlákno si mùeme pøedstavit odlehèenı proces, tj. pouze kód vlákna a zásobník, vše ostatní je sdíleno s ostatními vlákny tého procesu. Vlákno je tedy podmnoinou procesu a proces mùe vlastnit nìkolik vláken. Vlákno samo o sobì v systému existovat nemùe, musí k nìmu vdy existovat proces, se kterım sdílí všechna data, otevøené soubory, zpracování signálù. 

Pro implementaci vláken existují tyto modely: 


one-to-one - Implementace provedena na úrovni jádra. Kadé vlákno je pro jádro samostatnı proces, plánovaè procesù neèiní rozdíl mezi vláknem a procesem. Nevıhodou tohoto modelu mùe bıt velká reie pøi pøepínání vláken. 

many-to-one - Implementace provedena na úrovni uivatele, program si sám implementuje vlákna a vše okolo. Jádro o vláknech v procesech nemá ani tušení. Tento model se nehodí na víceprocesorové systémy, protoe vlákna nemohou bìet zároveò (kadé na jiném procesoru), jeden proces nelze nechat vykonávat na dvou procesorech. Vıhodou mùe bıt malá reie pøepínání vláken. 

many-to-many - Implementace provedena na úrovni jádra i uivatele. Tento model eliminuje nevıhody pøedchozích implementací (velká reie pøi pøepínání procesù, soubìnì nemùe bìet více vláken) a je proto pouit v mnoha komerèních UNIXech (Solaris, Digital Unix, IRIX). 
V Linuxu je pouit model první. Nevıhoda velké reie v podstatì není, protoe pøepínání procesù je v Linuxu implementováno velmi efektivnì. Pro tvorbu procesù a vláken se v Linuxu pouívá volání jádra clone(2), které ale pouívají pouze knihovny obhospodaøující vlákna. 

V zaèátcích, kdy se v Unixech zaèala vlákna objevovat, mìl kadı unixovı operaèní systém jiné aplikaèní rozhraní pro práci s vlákny, a proto byly programy špatnì pøenositelné. Proto vznikla norma POSIX, která mimo jiné také definuje aplikaèní rozhraní pro práci s vlákny (POSIX 1003.1c). Toto POSIXové rozhraní je dostupné i na OS Solaris 2.5, Digital Unix 4.0, IRIX 6. S kadou distribucí Linuxu postavenou na glibc-2.0 je dodávána knihovna pthread, která právì toto POSIXové aplikaèní rozhraní implementuje. 


Tvorba vláken a jejich ukonèení
Pro vytvoøení a ukonèení vlákna lze pouít následující funkce: 

int  pthread_create(pthread_t * thread, 
 pthread_attr_t * attr,
 void * (*start_routine)(void *), void * arg);


funkce vytvoøí nové vlákno, které bude vykonávat funkci start_routine, co je funkce akceptující jeden parametr typu void *. Na adresu thread je uloen identifikátor vlákna a jako atributy vlákna mùeme uvést NULL pro implicitní hodnoty. 

void pthread_exit(void *retval);


tato funkce pøedèasnì ukonèí vlákno, ze kterého byla funkce zavolána. 
Vlákno se také ukonèí, skonèí-li funkce start_routine. V obou pøípadech se pøedává návratovı kód. 


int pthread_join(pthread_t th, 
  void **thread_return);


funkce èeká na ukonèení vlákna th. Na adresu thread_return je uloen návratovı kód vlákna. 
Pøíklad, jak funkce pouít, naleznete na vıpise Pøíklad pouití vláken. 


#include <pthread.h>
#include <stdio.h>
#define ITEMS 10000

void * process(void *a){
      int i;
      printf("Process %s: start\n", (char *)a);
      for (i = 0; i<ITEMS; i++){
            printf("%s", (char *)a);
      };
      printf("Process %s: end\n", (char *)a);
      return NULL;
}

int main(){
      int retcode;
      pthread_t a,b;
      void * retval;

      retcode = pthread_create(&a, NULL, process, "A");
      if (retcode != 0) fprintf(stderr, "create a failed %d\n", retcode);
      retcode = pthread_create(&b, NULL, process, "B");
      if (retcode != 0) fprintf(stderr, "create b failed %d\n", retcode);
      retcode = pthread_join(a, &retval);
      if (retcode != 0) fprintf(stderr, "join a failed %d\n", retcode);
      retcode = pthread_join(b, &retval);
      if (retcode != 0) fprintf(stderr, "join b failed %d\n", retcode);
      return 0;
}

 



Vıpis è. 1: Pøíklad pouití vláken

Pøeklad programu
Pøi pøekládání programu, kterı pouívá vlákna, je tøeba tomuto pøizpùsobit hlavièkové soubory knihovny glibc tak, aby byly reentrantní. To provedeme definováním makra _REENTRANT. Dále je tøeba program slinkovat s knihovnou pthread. Pro pøeklad programu na vıpise Pøíklad pouití vláken pouijeme: 

 gcc -D_REENTRANT -o example1 example1.c -lpthread


Kritické sekce pomocí mutexu
Nejprve si polome otázku, co je to kritická sekce. Za kritickou sekci povaujeme tu èást kódu vlákna, která operuje nad sdílenımi daty a hrozí, e paralelnì mùe jiné vlákno operovat nad stejnımi daty. Dùsledkem mùe bıt nekonzistence dat. Napøíklad jedno vlákno zvıší sdílenou promìnnou A o jedna a dále s ní poèítá, kdeto druhé vlákno promìnou A zmenší o dvì a dále s ní poèítá. Pokud se poštìstí, tak se instrukce mohou proloit tak, e ani jedno vlákno nedá správnı vısledek. Tomuto je tøeba zabránit a to tím, e do té èásti, která pracuje s promìnnou A mùe vstoupit pouze jedno vlákno, druhé musí èekat a to první skonèí. Takovéto kritické sekce, kde mùe bıt v jednom okamiku pouze jedno vlákno, nazıváme MUTEX (MUTual EXclusion). Mutex má dva stavy - zamèenı (locked - nìkteré vlákno je uvnitø) a odemèenı (unlocked - v mutexu nikdo není). 
Pro práci s mutexy pouijeme funkce: 


int pthread_mutex_init(pthread_mutex_t *mutex, 
       const  pthread_mutexattr_t *mutexattr);


inicializace mutexu 

int pthread_mutex_lock(pthread_mutex_t *mutex);


zamèení mutexu. Po návratu je mutex vdy zamèen pro vlákno, které tuto funkci vykonalo. Pokud je mutex ji zamèen, funkce pozastaví vlákno a èeká na odemèení mutexu, aby následnì mutex zamkla a mohla nechat vlákno pokraèovat. 

int pthread_mutex_trylock(pthread_mutex_t *mutex);


pokus o zamèení mutexu. Pokud je mutex ji zamèen, funkce se vrátí s chybou EBUSY. 

int pthread_mutex_unlock(pthread_mutex_t *mutex);


odemèení mutexu 

int pthread_mutex_destroy(pthread_mutex_t *mutex);


uvolnìní zdrojù spojenıch s mutexem 
V pøíkladu Schematické znázornìní pouití mutexu mùete vidìt pouití mutexu. 


pthread_mutex_t mut_var;
...
/* Inicializace mutexu */
      pthread_mutex_init(&mut_var, NULL);
...
/* Vstup do mutexu */
      pthread_mutex_lock(&mut_var);
/* Vykonání operací nad sdílenımi daty */
...
/* Vıstup z mutexu */
      pthread_mutex_unlock(&mut_var);
...
/* Na konci programu zrušení mutexu */
      pthread_mutex_destroy(&mut_var);

 



Vıpis è. 2: Schematické znázornìní pouití mutexu
U mutexù se mùeme setkat s tím, e bude tøeba mutex zamknout v závislosti na podmínce. Napøíklad problém producent - konzument. Producent produkuje data do sdílené promìnné a konzument je ète. Pøitom promìnná musí bıt zabezpeèena mutexem a zároveò se musí hlídat stav, zda promìnná obsahuje uiteèná data. I na toto POSIX myslí, a to pomocí následujících funkcí: 


int pthread_cond_init(pthread_cond_t *cond, 
       pthread_condattr_t *cond_attr);


inicializace podmínky 

int pthread_cond_signal(pthread_cond_t *cond);


zpùsobí spuštìní jednoho vlákna, které èeká na podmínce. Jestlie neèeká ádné vlákno, funkce nemá ádnı efekt. Èeká-li více vláken, spustí se pouze jedno, ale není definováno jaké. 

int pthread_cond_broadcast(pthread_cond_t *cond);


zpùsobí spuštìní všech vláken èekajících na podmínce. Jestlie neèeká ádné vlákno, funkce nemá ádnı efekt. 

int pthread_cond_wait(pthread_cond_t *cond, 
       pthread_mutex_t *mutex);


automaticky odemkne mutex, pozastaví vlákno a èeká na signál od podmínky. Po pøíchodu signálu je mutex uzamèen a tato funkce ukonèena. Kadá podmínka musí bıt uzavøena v mutexu. 

int pthread_cond_timedwait(pthread_cond_t *cond,
       pthread_mutex_t *mutex, 
       const struct timespec *abstime);


je podobné pthread_cond_wait() s tím rozdílem, e èekání je èasovì omezeno. Pokud èas vyprší, pak je sekce uzamèena a funkce je ukonèena s chybou ETIMEDOUT. 

int pthread_cond_destroy(pthread_cond_t *cond); 


uvolní zdroje spojené s podmínkou 
V pøíkladu Pouití mutexu v problému producent - konzument mùete vidìt pouití mutexu a podmínek na problému producent - konzument. Všimnìte si rozdílné inicializace podmínek, samozøejmì obì podmínky jdou inicializovat stejnım zpùsobem. 


#include <pthread.h>
#include <stdio.h>
#include <stdlib.h>
#define ITEMS 100
#define NONVALID 0
#define VALID 1
pthread_mutex_t mut_var;
pthread_cond_t condvalid;
pthread_cond_t condnonvalid = PTHREAD_COND_INITIALIZER;
int valid;
int share;

void * konzument(void *a){
      printf("Process %s: start\n", (char *)a);
      while(1){
            pthread_mutex_lock(&mut_var);
            if (!valid)
              pthread_cond_wait(&condvalid, &mut_var);
            valid = NONVALID;
            printf("Process %s: %i\n", (char *)a, share);
            if (share == -1){
                  pthread_mutex_unlock(&mut_var);
                  break;
            };
            pthread_cond_signal(&condnonvalid);
            pthread_mutex_unlock(&mut_var);
      };
      printf("Process %s: end\n", (char *)a);
      return NULL;
}

void * producent(void *a){
      int i;
      printf("Process %s: start\n", (char *)a);
      for (i = 0; i<ITEMS; i++){
            pthread_mutex_lock(&mut_var);
            if (valid) 
              pthread_cond_wait(&condnonvalid, &mut_var);
            share = (int)rand();
            if (share == -1) share = 0;
            if (i == ITEMS - 1) share = -1;
            printf("Process %s: %i\n", (char *)a, share);
            valid = VALID;
            pthread_cond_signal(&condvalid);
            pthread_mutex_unlock(&mut_var);
      };
      printf("Process %s: end\n", (char *)a);
      return NULL;
}

int main(){
      pthread_t a,b;
      pthread_mutex_init(&mut_var, NULL);
      pthread_cond_init(&condvalid, NULL);
      pthread_create(&a, NULL, producent, "producent");
      pthread_create(&b, NULL, konzument, "konzument");
      pthread_join(a, NULL);
      pthread_join(b, NULL);
      pthread_cond_destroy(&condvalid);
      pthread_cond_destroy(&condnonvalid);
      pthread_mutex_destroy(&mut_var);
      return 0;
}

 



Vıpis è. 3: Pouití mutexu v problému producent - konzument

Kritické sekce pomocí semaforù
Semafory se pouívají pro podobnı úèel jako mutexy, a to pro kontrolování vstupu do kritickıch sekcí. Ale na rozdíl od mutexu, kdy v sekci mùe bıt pouze jeden, se semafory lze docílit, e v sekci mùe bıt více vláken. Semafor si mùeme pøedstavit jako poèítadlo s poèáteèní hodnotou, kterou nastaví uivatel. Vdy pøi vstupu do kritické sekce se èeká, dokud není hodnota semaforu vìtší ne nula. Pokud je, pak se hodnota zmenší o jednu a vstoupí se do kritické sekce. Na konci sekce se hodnota semaforu o jednièku zvedne. Pro práci se semafory pouíváme funkce: 

int sem_init(sem_t *sem, int pshared, 
       unsigned int value);


inicializace semaforu. Argument pshared urèuje, zda je semafor lokální pro tento proces (hodnota 0) nebo je sdílen mezi procesy (hodnota != 0). V Linuxu jsou podporovány pouze lokální semafory. 

int sem_wait(sem_t * sem);


slouí pro vstup do kritické sekce. Pokud je sekce obsazena (semafor == 0), pak se èeká a se sekce uvolní. 

int sem_trywait(sem_t * sem);


slouí pro vstup do kritické sekce. Je-li sekce obsazena, funkce se vrátí s chybou EAGAIN. 

int sem_post(sem_t * sem);


slouí k ukonèení kritické sekce. 

int sem_getvalue(sem_t * sem, int * sval);


vrátí hodnotu semaforu. 

int sem_destroy(sem_t * sem);


uvolní všechny zdroje spojené se semaforem. 

#include <pthread.h>
#include <stdio.h>
#include <stdlib.h>
#include <semaphore.h>
#define ITEMS 100

sem_t semfull;
sem_t semempty;
int share;

void * konzument(void *a){
  printf("Process %s: start\n", (char *)a);
  while(1){
    sem_wait(&semfull);
    printf("Process %s: %i\n", (char *)a, share);
    if (share == -1){
      sem_post(&semempty);
      break;
    };
    sem_post(&semempty);
  };
  printf("Process %s: end\n", (char *)a);
  return NULL;
}

void * producent(void *a){
  int i;
  printf("Process %s: start\n", (char *)a);
  for (i = 0; i<ITEMS; i++){
    sem_wait(&semempty);
    share = (int)rand();
    if (share == -1) share = 0;
    if (i == ITEMS - 1) share = -1;
    printf("Process %s: %i\n", (char *)a, share);
    sem_post(&semfull);
  };
  printf("Process %s: end\n", (char *)a);
  return NULL;
}

int main(){
      pthread_t a,b;

      sem_init(&semfull, 0, 0);
      sem_init(&semempty, 0, 1);
      pthread_create(&a, NULL, producent,
          "producent");
      pthread_create(&b, NULL, konzument, 
          "konzument");
      pthread_join(a, NULL);
      pthread_join(b, NULL);
      sem_destroy(&semfull);
      sem_destroy(&semempty);
      return 0;
}

 



Vıpis è. 4: Pouití semaforù u problému producent - konzument
Toto rozhraní pro semafory definuje norma POSIX 1003.1b a POSIX 1003.1i. 


Ukonèení vlákna jinım vláknem
int pthread_cancel(pthread_t thread);


vyvolá poadavek na zrušení vlákna. 

int pthread_setcancelstate(int state,
      int *oldstate);


nastaví chování vlákna, které tuto funkci vyvolalo, na poadavek jeho zrušení. Moné jsou dva stavy: PTHREAD_CANCEL_ENABLE a PTHREAD_CANCEL_DISABLE. 

int pthread_setcanceltype(int type, int *oldtype);


nastaví, kdy je mono vlákno zrušit. Moné jsou dvì nastavení: PTHREAD_CANCEL_ASYNCHRONOUS - vlákno bude zrušeno skoro okamitì po pøijetí poadavku nebo PTHREAD_CANCEL_DEFERRED - vlákno se zruší a v okamiku, kdy dojde do bodu, kde je mono vlákno zrušit. Jako body jsou v POSIXu definovány tyto funkce: pthread_join(3), pthread_cond_wait(3), pthread_cond_timedwait(3), pthread_testcancel(3), sem_wait(3), sigwait(3). 

void pthread_testcancel(void);


tato funkce pouze testuje, zda byl pøijat poadavek na zrušení vlákna. Pokud pøijat byl, vlákno je zrušeno, v opaèném pøípadì se funkce normálnì vrátí. Funkce se pouívá v místech, kde jsou dlouhé kusy kódu bez bodù vhodnıch pro zrušení. 
Pokud je vlákno v bodu vhodném pro zrušení (viz pthread_setcanceltype(3)) a pøijalo poadavek na zrušení, bude zrušeno. Toté se stane, pokud pøijalo poadavek na zrušení a a následnì vejde do bodu vhodného pro zrušení (pouze pøi nastaveném PTHREAD_CANCEL_DEFERRED). 

Pokud se ukonèí hlavní vlákno, ani by poèkalo na vlákna jím vytvoøená, jsou tato vlákna ukonèena také. 

Jak pouít funkce mùete vidìt na pøíkladu Ukonèení vlákna. 


#include <pthread.h>
#include <stdio.h>
#include <unistd.h>
#include <semaphore.h>

sem_t sem;

void * process(void *a){
   printf("Proces entered\n");
   sem_wait(&sem);
   printf("Proces exiting\n");
   return NULL;
}

int main(){
   pthread_t thid;
   void * thretval;

   sem_init(&sem, 0, 0);

   pthread_create(&thid, NULL, process, NULL);

   sleep(5); /* Vlákno se zatím rozbìhne */ 
   if (pthread_cancel(thid) != 0)
     printf("Cancel error\n");

   pthread_join(thid[i], &thretval);
   if (thretval != PTHREAD_CANCELED)
     printf("Thread not be canceled.\n", i);

   return 0;
}

 



Vıpis è. 5: Ukonèení vlákna

Další uiteèné funkce
pthread_t pthread_self(void);


vrací identifikátor vlákna, které tuto funkci vyvolalo. 

int pthread_equal(pthread_t thread1,
      pthread_t thread2);


porovná, zda se identifikátory vláken rovnají. 

int pthread_detach(pthread_t th);


odpojí vlákno. Všechny pamìové prostøedky, které vlákno pouívá, budou po ukonèení vlákna okamitì uvolnìny. S odpojenım vláknem se nelze synchronizovat a vyzvednout jeho návratovı kód funkcí pthread_join(3). 

int pthread_attr_init(pthread_attr_t *attr);


inicializuje objekt atributù na implicitní hodnoty. Tento objekt se dá pouít pro vytvoøení více vláken. 

int pthread_attr_destroy(pthread_attr_t *attr);


uvolní všechny prostøedky potøebné pro objekt atributù. 

Problémy, do kterıch se mùete dostat
knihovna pro vlákna pouívá signály SIGUSR1 a SIGUSR2, proto je program pouívat nemùe. 

pokud budete vlákna pouívat v X aplikacích, je tøeba mít Xlib kompilovánu s -D_REENTRANT a podporou vláken (knihovna musí bıt napsána reentrantnì - více vláken mùe vykonávat tuté funkci ve stejnou chvíli, bez vzájemného ovlivnìní - funkce nepouívají globální promìnné). Toté platí o jakékoliv knihovnì, kterou budete v programu pouívat. Pokud knihovna takto reentrantní není, je mono ji pouívat, ale pouze z hlavního vlákna (kódu procesu). Toto souvisí s promìnnou errno. Kadé vlákno má toti vlastní, pouze hlavní vlákno pouívá globální errno. 

pouívání vláken v C++ s libg++ asi nebude fungovat. Pro pouívání vláken v C++ je doporuèen pøekladaè egcs a knihovna libstdc++. 

pokud program vytvoøí napøíklad 2 vlákna, nedivte se, e vidíte 4 stejné procesy. Jeden je hlavní proces, pak vidíte 2 vlákna a poslední je vlákno starající se o správnı chod vláken. Toto vlákno je vytvoøeno knihovnou pthread. 

Odkazy
Na adrese http://www.serpentine.com/~bos/threads-faq/ lze najít èasto kladené otázky newsové skupiny comp.programming.threads. 
Bliší informace o linuxovıch vláknech naleznete na adrese http://pauillac.inria.fr/~xleroy/linuxthreads. Lze zde také najít tutorial. 

Na adrese http://www.rdg.opengroup.org/onlinepubs/7908799/index.html najdete X/Open Group Single Unix specification, kde by se mìl také dát najít bliší popis aplikaèního rozhraní pro vlákna. 

Na adrese http://www.cs.wustl.edu/~schmidt/ACE.html najdete projekt, kterı také usnadòuje pouívání vláken v C++.  
 

