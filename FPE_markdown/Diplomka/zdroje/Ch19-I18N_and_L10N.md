---
title: "Ch19-I18N_and_L10N.htm"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/zdroje/Ch19-I18N_and_L10N.htm"
date: 2010-02-02
type: HTML
---

::: Section1
Internationalization and Localization

The Internet has no boundaries and neither should your web application.
People all over the world access the Net to browse web pages that are
written in different languages. For example, you can check your
web-based email from virtually anywhere. A user in Japan can access the
web and check her Yahoo! Email in Japanese.[  ]{style=""}How does Yahoo
do it? Is it because the user's machine has a Japanese operating system
or do web-based applications automatically adjust according to the
users' region?

[      ]{style=""}Welcome to the twin worlds of Internationalization and
Localization. What *are* they and why do we need them?[  ]{style=""}This
chapter attempts to answer these questions and shows you how to
internationalize and localize your J2EE web applications. Each of these
terms is explained in detail in the subsequent sections of this chapter.
At the end of this chapter you will be able to see how to make your web
application user friendly in different countries using different
languages. You will also see the various ways to do this as well as some
common dos and don'ts when internationalizing your applications.

[      ]{style=""}In section 19.1, we will explain the basics of
Internationalization and localization; their need and their advantages.
In section 19.2 you will learn more about character encodings, what they
are and how to use them. Section 19.3 deals with web tier
internationalization and the various ways you can achieve this. Some of
the approaches include Struts, JSTL tags, Java server faces and Tiles
localization. Finally, in section 19.4 you will see some
internationalization best practices.

8.1[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Internationalization
and Localization

When you read about internationalizing applications, you will come
across terms such as localization, character encoding, locales, resource
bundles and so on. This section covers some of the commonly used terms
in this chapter.

Internationalization or I18n is the process of enabling your application
to cater to users from *different* countries and supporting *different*
languages. With I18n, software is made portable between languages or
regions. For example, the Yahoo! Web site supports users from English,
Japanese and Korean speaking countries, to name a few.

Localization or L10n on the other hand, is the process of customizing
your application to support a *specific* location. When you customize
your web application to a specific country say, Germany, you are
localizing your application. Localization involves establishing on-line
information to support a specific language or region. Though I18n and
L10n appear to be at odds with each other, in reality they are closely
linked. The later sections in this chapter will show you how.

A Locale is a term that is used to describe a certain region and
possibly a language for that region. In software terms, we generally
refer to applications as supporting certain *locales.* For example, a
web application that supports a locale of "fr_FR" is enabling
French-speaking users in France to navigate it. Similarly a locale of
"en_US" indicates an application supporting English-speaking users in
the US.

A ResourceBundle is a class that is used to hold locale specific
information. In Java applications, the developer creates an instance of
a ResourceBundle and populates it with information specific to each
locale such as text messages, labels, and also objects. There will be
one ResourceBundle object per locale.

A Character Encoding is a mapping between characters and values. In
order for your web application to support multiple languages, you will
first have to ensure that the appropriate encoding is supported by your
application code as well as the back-end database. Typical encodings
include the Unicode format, which is a 16 bit format that supports most
of the world's major languages and the DBCS format that is the Double
Byte Character Set format that can hold two bytes of data per character.
The Chinese language is represented using the DBCS format.

The thought process behind developing an internationalized web
application is quite complex. It is a matter of setting priorities in
order to develop an application whose complexity can be considerably
increased based on the number of countries and languages it has to
support. This means that whether you are developing a web application
from scratch or modifying an existing one, you will have to identify the
various factors that will drive the move towards internationalization.
Section 19.1.1 shows the various factors to be considered.

19.1.1 Internationalization factors

Normally, when a web application is being developed,
internationalization is not given very much importance, as the focus is
more on "getting the application working" and then maybe later on
supporting different locales. Though this is not recommended, it might
still work as long as the application is small and can take on the
changes that follow after deployment for a particular (default) locale.

But, what if the application is very complex, with a large number of JSP
pages and the requirement is to support multiple locales? What factors
should you consider before taking the actual step of changing your code
to do this? Here are a few:

1.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Identify
the areas in your application that will have to change in order to
support users from different countries. There are two main areas that
will need change:

a.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}The
visible part of your application -- the User Interface. The user
interface specific changes could mean changes to text, date formats,
currency formats etc. More information about this is provided in section
19.1.3

b.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}The
invisible parts of your application -- database support for different
character encoding formats and your back-end logic that processes this
data.

2.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Identify
the prospective clientele of your application. A country that may not
seem to be at the top of your list right now might actually be a good
bet based on the size of it's population. For example, the new
generation of young adults in India is turning out to be a growing
consumer of foreign products. Companies like Nokia and Coke are cashing
in on this trend. Similarly, web applications have to be flexible enough
to support different locales. It never helps to have to go back and
change your design in order to accommodate new locales or any other
internationalization specific changes.

3.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Once
the end user has been identified, see if your software supports their
language-based needs. For example, do you have the software to develop a
web based search engine that accepts input in Arabic and returns search
results?

4.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Identify
a timeline within which you will have to deliver the web application
with support for a given region *and* language. For example, the support
for the French language in France (fr_FR) is different from the support
for French in Canada (fr_CA) in terms of the presentation details. For
example: the following code segment formats the same number for two
different locales both speaking French.

[   ]{style=""}[   ]{style=""}// for France

[   ]{style=""}[   ]{style=""}Locale loc1 = new Locale(\"fr\", \"FR\");

[   ]{style=""}[   ]{style=""}NumberFormat frenchFmt =
NumberFormat.getCurrencyInstance(loc1);

[   ]{style=""}[   ]{style=""}double amtFR = 5010.78;

[   ]{style=""}[   ]{style=""}System.out.println(currFmt.format(amtFR));

 

[   ]{style=""}[   ]{style=""}// for Canada

[   ]{style=""}[   ]{style=""}Locale loc2 = new Locale(\"fr\", \"CA\");

[   ]{style=""}[   ]{style=""}NumberFormat canFmt =
NumberFormat.getCurrencyInstance(loc2);

[   ]{style=""}[   ]{style=""}double amtCA = 5010.78;

[   ]{style=""}[   ]{style=""}System.out.println(currFmt.format(amtCA));

 

And the output looks like:

[   ]{style=""}[   ]{style=""}5 010,78 €

[   ]{style=""}[   ]{style=""}5 010,78 \$

This example shows the first output in Euros whereas the second output
indicates the same amount in Canadian dollars. This is just one of the
many differences you will come across. If you dig deeper into the
intricacies of each locale specific format, you will find that even
though two regions might have a common language, they differ in almost
every other respect when it comes to displaying data.

The Locale and NumberFormat classes are explained in more detail in
section 19.1.4

 

5.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}The
last but also the most important factor is to identify the actual "type"
of internationalization approach to use. That is, do you want to create
a new copy of each JSP page per locale or do you want to have a single
JSP page that works for different locales. The former approach (Figure
19.1) is only suitable for smaller applications with support for a few
languages. If you are developing a new application or internationalizing
a large application with support for multiple locales, then the latter
approach (Figure 19.2) is recommended.[                      
]{style=""}

![](Ch19-I18N_and_L10N_files/image002.jpg){v:shapes="_x0000_s1185"
height="199" width="478"} 

 

 

 

 

 

 

 

\

Figure 19.1 The "One JSP page per locale" approach

[ ]{style=""}

  -- ----------------------------------------------------------------------------------------------
     
     ![](Ch19-I18N_and_L10N_files/image004.jpg){v:shapes="_x0000_s1189" height="114" width="442"}
  -- ----------------------------------------------------------------------------------------------

 

 

 

 

 

 

\

Figure 19.2 Same JSP supports multiple
locales[]{style="font-weight: normal;"}

 

19.1.2 Advantages of Internationalization and Localization

Having to internationalize a web application is not an easy task, as you
will need to know exactly what areas of your application will have to
change and update them. This means additional effort, time and cost.
Many companies that decide to go global have some specific goals in mind
that justify the cost. Here are a few main ones:

1.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}An
increase in the number of users as more and more people will be able to
use the application in their native languages, all this without having
to create a single office in each of the regions supported. The mantra
of any profit making company is quite simple actually and works well for
internationalizing applications too: More users = More sales = More
profit.

2.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Though
the cost of localization is high as each individual page will have to be
translated into several languages but the benefits from sales almost
always outweigh the costs. A lot of big companies in the US, Sun
Microsystems included, obtain around half of their revenue from outside
of the US.

3.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}By
localizing a web application, the user level of comfort with the
application increases. The primary aim of localization is to "get
through" to the user. And what better way to do this than in a language
that the user is comfortable with?

In this section you saw what you can gain by Internationalizing your
application. The next section explains the various parts of your
application that can be internationalized.

19.1.3 What can be localized?

So far you have seen what internationalization and localization are, and
what they can do for us. In this section you will see what parts of your
web application will have to be customized in order to support different
locales.

[      ]{style=""}Before we move on to the actual details we will see a
simple example that might aid in understanding the need for localization
better.

[      ]{style=""}

Consider a simple "Hello World" example just for a moment. Most users
write their first web applications (read servlets, JSPs) to display the
time honored Hello World message. Then they move on to challenging tasks
that, say take the user's name from a HTML form and display a more
personalized message like "Welcome to ABC Bank, John Doe". Consider the
application from a user's point of view. When your application runs
anywhere in the US, everyone, well almost everyone speaks English and
hence, they won't have any trouble trying to figure out what your
application is trying to say.

[      ]{style=""}Now, consider the same application being accessed by a
user in a non-English speaking country say Japan. There is a good chance
that the very same message might not make too much sense to a Japanese
user. Why not? Simple, English is not spoken in many countries and such
countries use their own languages to communicate, in their talks, their
books and surprise!, in their websites too.

[      ]{style=""}The point in context is very simple: Present your web
application to foreign users in a way they can comprehend it and
navigate freely without facing any language barriers.

[      ]{style=""}Great, now you know where this is leading, right?
That's right, localization! In order to localize your web application,
you have to identify the key areas that will have to change. You had
seen in the previous section that there are two main areas: the User
interface and the back end logic (and possibly database encoding
support). In this section we focus on the UI specific changes required
to localize your web application.

Here is a list of the commonly localized fields in a web application:

1.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Messages
-- These could be status messages displayed to the user or error
messages

2.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Labels
on GUI components -- labels, button names

3.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Dates

4.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Times

5.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Numbers

6.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Currencies

7.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Phone
numbers

8.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Addresses

9.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Graphics
-- images have to be very specific for every locale and cater to each
region's cultural tastes.

10.[  
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Icons

11.[  
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Colors
-- Colors play a very important role in different countries. For
example, death is represented by the color white in China.

12.[  
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Sounds

13.[  
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Personal
titles

14.[  
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Page
layouts -- that's right. Just like colors, page layouts can vary from
locale to locale based on the country's cultural preferences.

There are other properties that you might require to be localized, but
the ones mentioned are the commonly used ones. You will see in the next
section a brief overview of the Java Internationalization API and some
examples on how to update some of these fields dynamically based on
locale information.

 

19.1.4 The I18n and L10n API: a brief overview

Java provides an easy-to-use API for internationalizing applications.
This section briefly covers some of the important topics in the API as
related to its use in the subsequent sections. If you need more
information on the various API specifics, please refer to the links
provided in the Resources section at the end of this chapter.

[      ]{style=""}In order to localize any application, client-side or
server-side, you will need to know how to use some of the
internationalization specific classes in the java.util and java.text
packages. This section shows some of the commonly used classes and their
functions. Figure 19.3 shows the classes in the Java I18n API. If you
are already familiar with the Java Internationalization API, you can
skip this section and proceed to the next section "Internationalization
and the web tier".

[ ]{style=""}

  -- ----------------------------------------------------------------------------------------------
     
     ![](Ch19-I18N_and_L10N_files/image006.jpg){v:shapes="_x0000_s1173" height="192" width="624"}
  -- ----------------------------------------------------------------------------------------------

 

 

 

 

 

 

 

 

[ ]{.underline}

\

Figure 19.3 TheI18n classes provided by the Java Internationalization
API

java.util.Locale[  ]{style=""}

The Locale class represents a specific geographical or cultural region.
It contains information about the region and its language and sometimes
a variant specific to the user's system. The variant is vendor specific
and can be WIN for a Windows system, MAC for a Macintosh etc. The
following examples show you how to create a Locale object for different
cases:

 

A Locale object that describes only a language (French):

[     ]{style=""}Locale frenchSpeakingLocale = new Locale(\"fr\", \"\");

[      ]{style=""}

A Locale object that describes both the spoken language and the country
(French Canada):

[     ]{style=""}Locale canadaLocale = new Locale(\"fr\", \"CA\");

 

A Locale object that describes the spoken language, country and a
variant representing the user's operating system (French Canada and
Windows Operating system):

[     ]{style=""}Locale canadaLocaleWithVariant = new Locale(\"fr\",
\"CA\", \"WIN\");

 

[ ]{.underline}

java.util.ResourceBundle

ResourceBundle is an abstract base class that represents a container of
resources. It has two subclasses: ListResourceBundle and
PropertiesResourceBundle. When you are localizing your application, all
the locale specific resources like text-messages, icons and labels are
stored in subclasses of the ResourceBundle. There will be *one* instance
of the ResourceBundle per locale.

The [getBundle]{style="font-size: 10pt; font-family: Courier;"} method
in this class retrieves the appropriate ResourceBundle instance for a
given locale. The location of the right bundle is implemented using an
algorithm which is explained later in this section.

Let us see how a resource bundle instance is retrieved with a simple
example. Consider a custom ResourceBundle subclass called
ABCBankResources that will contain data specific to your application. In
this example, you will see how to use PropertyResourceBundles assuming
that all the resources to be localized are strings. In order to use
PropertyResourceBundle, you will have to create java Properties files
that will hold the data in key = value format.

 

Listing 19.1 shows ABCBankResources.properties containing strings to be
localized, for the default locale. (en_US)

 

Listing 19.1 ABCBankResources.properties

[  ]{style=""}header.title=ABC Bank

 

Listing 19.2 shows ABCBankResources_fr_FR.properties containing the
strings to be localized, for a language "fr" and region of "FR" (France)

 

Listing 19.2 ABCBankResources_fr_FR.properties

[  ]{style=""}header.title=Banque de ABC

 

Now we have the properties files ready to go. In order to use the data
in these files, you will have to get the ResourceBundle instance as
shown in Listing 19.3.

     

Listing 19.3 Extracting data from a resource bundle

[  ]{style=""}Locale myLocale = new Locale(\"fr\",\"FR\");

[  ]{style=""}// Get the resource bundle for myLocale

[  ]{style=""}**ResourceBundle abcBankBundle =
ResourceBundle.getBundle(**

**[                                     
]{style=""}\"ABCBankResources\",**

**[                                       ]{style=""}myLocale);**

[  ]{style=""}// Get the localized strings from this resource bundle

[  ]{style=""}String myHeader =
**abcBankBundle.getString(\"header.title\");**

[  ]{style=""}System.out.println(myHeader);

[ ]{style="font-size: 10pt; font-family: Courier;"}

Listing 19.3 will produce an output "Banque de ABC". What if the
ABCBankResources_fr_FR.properties file was missing? What would it print
then? Just to see what happens, rename the file to something else and
run the program again. This time the output will be "ABC Bank". But the
locale was "fr_FR"\![  ]{style=""}

Here's what happened. Because the locale was "fr_FR", the getBundle
method looked up ABCBankResources_fr_FR.properties. When it did not find
this file, it looked for the "next best match" that is
ABCBankResources_fr.properties". But this file doesn't exist either.
Finally the getBundle found the ABCBankResources.properties file and
returned an instance of PropertiesResourceBundle for this file. Hence
the header string myHeader is looked up using the "header.title" key
from the ABCBankResources.properties file and returned to the user.

 

In general, the algorithm for looking up a Properties file is:

 

[ 
]{style=""}ABCBankResources*\_***language_country_variant***.*properties

[  ]{style=""}ABCBankResources*\_***language_country**.properties

[  ]{style=""}ABCBankResources*\_***language**.properties

[  ]{style=""}ABCBankResources.properties

 

The properties file of format xxx_language_country_variant.properties is
looked for first. If not found, then xxx_language_country.properties is
looked up. Similarly the lookup order goes as xxx_language.properties
and finally xxx.properties. If none of the files are found, then an
error message is displayed.

 

**[Note:]{.underline}** Java Properties files are commonly used in web
tier localization for both Struts and JSTL web applications. Hence we
have shown you how to use them for localizing string data. If your
requirement involves extracting locale specific resources besides
strings, you might want to use the ListResourceBundle class.

 

java.text.NumberFormat

NumberFormat is an abstract base class that is used to format and parse
numeric data specific to a locale.

This class is used primarily to format numbers and currencies. A sample
example that formats currencies is shown in listing 19.4

 

Listing 19.4 Formatting currencies using NumberFormat

[ ]{style=""}Locale frLocale = new Locale (\"fr\",\"FR\");[  
]{style=""}

[ ]{style=""}// get instance of NumberFormat

[ ]{style=""}NumberFormat currencyFormat =
NumberFormat.getCurrencyInstance(frLocale);

 

[ ]{style=""}double salaryAmount = 5124.75;

[ ]{style=""}// Format the amount for the French locale

[ ]{style=""}String salaryInFrench =
currencyFormat.format(salaryAmount);

[ ]{style=""}System.out.println (\"Salary is: \" + salaryInFrench);

 

The output:

[ ]{style=""}Salary is: 5 124,75 €

** **

On the other hand, if a user in France enters a currency in the French
format into a text field, the NumberFormat class can be used to
interpret the amount correctly. Listing 19.5 shows how using the
formatted amount we had obtained in Listing 19.4.

 

Listing 19.5 Formatting currencies using NumberFormat

[   ]{style=""}// get the amount from a text field (5 124,75 €)

[   ]{style=""}String salaryInFrench = salaryField.getText();

[   ]{style=""}// Print it back into a regular number

[   ]{style=""}System.out.println(currencyFormat.parse(salaryInFrench);

 

The output:

[   ]{style=""}5124.75

There is a subclass of the NumberFormat class called DecimalFormat which
can be used to format locale specific decimal numbers with the
additional capability of providing patterns and symbols for formatting.
The symbols are stored in a DecimalFormatSymbols object. When using the
NumberFormat factory methods, the patterns and symbols are read from
localized resource bundles.

java.text.DateFormat

DateFormat is an abstract class that is used to format dates and times.
When a locale is specified it formats the dates accordingly.

 

The following code formats a date independent of locale

[   ]{style=""}Date now = new Date();

[   ]{style=""}String dateString =
DateFormat.getDateInstance().format(now);

 

To format a date for a given locale:

[   ]{style=""}DateFormat dateFormat =
DateFormat.getDateInstance(Locale.GERMANY);

[   ]{style=""}dateFormat.format(now);

 

java.text.MessageFormat

MessageFormat is used to create concatenated messages in a language
neutral way. It takes a set of input objects, formats them and inserts
the formatted strings into specific places in a given pattern.

The following code shows how inserting string objects into specific
locations creates a message:

[ ]{style="font-family: Courier; color: windowtext;"}

Object\[\] myObjects = { \"John\", \"Doe\" , new[      
]{style=""}java.util.Date(System.currentTimeMillis()) };

 

[   ]{style=""}String messageToBeDisplayed = \"{0} {1} logged in at
{2}\";

String message = java.text.MessageFormat.format(messageToBeDisplayed,[  
]{style=""}myObjects);

 

[   ]{style=""}System.out.println(message);

 

When you run the program, you will get the following output:

[[   ]{style=""}John Doe logged in at 8/28/03 2:57
PM]{style="background: white none repeat scroll 0% 0%; -moz-background-clip: border; -moz-background-origin: padding; -moz-background-inline-policy: continuous;"}

 

java.text.Collator

In any localized application if you need to sort strings in the native
language, the good old sorting functions that we use to sort ASCII
strings will not be sufficient because of the nuances of each language.
The Collator class in the java.text package is used to perform locale
specific string comparison. This class builds alphabetical sorting and
searching routines for natural language programs. Listing 19.6 shows you
how to sort an array of strings for a given locale.

 

Listing 19.6 Sorting strings using the Collator

[  ]{style=""}ArrayList stringArray = new ArrayList();

[  ]{style=""}stringArray.add(\"péché\");

[  ]{style=""}stringArray.add(\"pêche\");

[  ]{style=""}stringArray.add(\"bat\");

[  ]{style=""}stringArray.add(\"Tofu\");

[  ]{style=""}stringArray.add(\"Töne\");

[  ]{style=""}stringArray.add(\"BAT\");

[  ]{style=""}stringArray.add(\"Bat\");

 

[  ]{style=""}Locale frLocale = new Locale(\"fr\",\"FR\");

[  ]{style=""}Collator myCollator = Collator.getInstance(frLocale);

[  ]{style=""}Collections.sort(stringArray,myCollator);

 

[  ]{style=""}System.out.println(stringArray);[  ]{style=""}

 

The output:

[  ]{style=""}\[bat,Bat,BAT,péché,pêche,Tofu,Töne\]

 

In this example you saw how the Collator object can be used to sort
Strings in natural language programs. This class is very powerful and
can go into extreme detail when processing Strings. It can have several
levels of decomposition and strength which can be used to further refine
the search and sort capabilities.

You can set a Collator's *strength* to determine the level of difference
for comparisons. To get more information about this class, you can look
up the Collator API on Sun's site at:

[     
]{style=""}http://java.sun.com/j2se/1.4.1/docs/api/java/text/Collator.html

**[ ]{.underline}**

native2ascii conversion utility

Java programs can process only those files that are encoded in Latin-1
encoding or files in Unicode encoding. Any other files containing
different encodings besides these two will not be processed.

The native2ascii tool is used to convert such non Latin-1 or non-Unicode
files into a Unicode encoded file.

For example, if you have a file encoded in a different language, say
myCyrillicFile which is in Cyrillic, you can use the native2ascii tool
to convert it into a Unicode encoded file as follows:

 

[   ]{style=""}native2ascii --encoding UTF-8 myCyrillicFile
myUnicodeFile

[ ]{.underline}

[Note:]{.underline} You can use other encodings besides UTF-8 too.

 

This section covered the basics of the Java Internationalization API. In
the next section you will learn about Character encoding and how it
applies to web applications.

8.2[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Character
encoding

Earlier, when applications were built, they were built for one language.
Those were the days of "code pages". Code pages described how binary
values mapped to human readable characters. A currently executing
program was considered to be in a single code page. These approaches
were fine until Internationalization came along. Then came the issue of
how to represent multiple character sets and encodings for an
application. Hence came character sets and encodings. This section gives
a brief overview of both in the context of a web application.

8.2.1[           
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Character
sets

Character sets are sets of text and graphic symbols mapped to positive
integers. ASCII was one of the first character sets to be used. ASCII
though efficient, was good at representing only US English.

[      ]{style=""}Unicode, which came soon after, was more efficient as
it defined a standardized character set that represented most of the
commonly used languages. In addition, it could be extended to
accommodate any additions. Unicode characters can be represented as
escape sequences of type \\u*XXXX* where XXXX is a character's 16 bit
representation in hexadecimal in cases where a Java program's source
encoding is not Unicode compliant.

 

8.2.2[           
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Character
encoding

A Character encoding, as mentioned earlier, maps a character to fixed
width units. It also defines ordering rules and byte serializing
guidelines. Different character sets have multiple encodings. For
example, Java programs represent Cyrillic character sets using KO18-R or
KO18-U encodings. Unicode enables us to write multilingual applications.

[      ]{style=""}Other examples of encodings include ISO 8859, UTF-8
etc. UTF or Unicode Transformation Format is used to encode 16 bit
Unicode characters as one to four bytes. A UTF byte is equivalent to
7-bit ASCII if its higher order bit is zero. You might have come across
many JSP pages, which have a line that looks like:

[  ]{style=""}\<%@ page contentType=\"text/html;charset=UTF-8\"
language=\"java\" %\>

Here, charset=UTF-8 indicates that the page uses a response encoding of
UTF-8.

When internationalizing the web tier, you need to consider three types
of encodings:

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}Request
encoding

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}Page
encoding

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}Response
encoding

[ ]{.underline}

Request Encoding

Request encoding deals with the encoding used to encode request
parameters. Browsers typically send the request encoding with the
*Content-type* header. If this is not present, the servlet container
will use ISO-8859-1 as the default encoding.

 

Page Encoding

Page encoding is used in JSP pages to indicate the character encoding
*for that file.* You can find the page encoding from:

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}The
Page Encoding value of a JSP property group whose URL pattern matches
the page. To see how JSP property groups work, you can go to the
following url:

[                        ]{style=""}[    
]{style=""}http://java.sun.com/j2ee/1.4/docs/tutorial/doc/JSPIntro13.html#wp72193

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}The
pageEncoding attribute in a JSP page specified along with the page
directive. If the value pageEncoding attribute differs from the value
specified in the JSP property group, a translation error can occur.

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}The
CHARSET value of the contentType attribute in the page directive.

[Note:]{.underline} If none of these encodings are mentioned, then the
default encoding of ISO-8859-1 is used.

 

Response Encoding

Response encoding is the encoding of the text response sent by a servlet
or a JSP page. This encoding governs the way the output is rendered on a
client's browser and based on the client's locale. The web container
sets a response encoding from one of the following:

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}The
CHARSET value of the contentType attribute in the page directive.

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}The
encoding in the pageEncoding attribute of the page directive

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}The
Page Encoding value of a JSP property group whose URL pattern matches
the page

[Note:]{.underline} If none of these encodings are mentioned, then the
default encoding of ISO-8859-1 is used.

 

Problems with legacy encodings:

Early on, when internationalization of computer applications became
popular, there was a boom in the number of encodings available to the
user. Unfortunately these encodings were unable to cover multiple
languages. For example: the European Union was not able to cover all the
European languages in one encoding, resulting in having to create
multiple encodings to cover them. This further worsened the problem as
multiple encodings could use the *same* number to represent *different
characters* in different languages. The result: higher chances of data
corruption.[  ]{style=""}

[      ]{style=""}A big company had its applications working great with
a default locale of US English, until it decided to go global. One of
the requirements was to support Chinese characters. The application code
was modified accordingly but each time the application ran, it was just
not able to produce meaningful output, as the text seemed to be
distorted. The culprit was the database encoding.

[      ]{style=""}Chinese characters, just like Korean and Japanese,
have writing schemes that cannot be represented by single byte code
formats such as ASCII and EBCDIC. These languages need at least a Double
Byte Character Set (DBCS) encoding to handle their characters. Once the
database was updated to support DBCS encoding, the applications worked
fine.

[      ]{style=""}These problems led to the creation of a universal
character-encoding format called Unicode.

[ ]{.underline}

Unicode

Unicode is a 16 bit character encoding that assigns a unique number to
each character in the major languages of the world. Though it can
officially support up to 65,536 characters, it also has reserved some
code points for mapping into additional 16-bit planes with the potential
to cope with over a million unique characters.[  ]{style=""}Unicode has
several advantages, but before we go into them, here's what the official
Unicode web site ([http://www.unicode.org](http://www.unicode.org/)) has
to say about Unicode:

*Unicode provides a unique number for every character,\
no matter what the platform,\
no matter what the program,\
no matter what the language.*

Advantages of Unicode

1.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Unicode
provides support for multiple languages in different encoding formats

2.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Easy
to incorporate into client-server or multi-tier applications

3.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Offers
significant cost savings over legacy character sets

4.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}And
most important of all, it enables a single web application to service
users across multiple platforms, languages and countries without any
modification.

The past few sections covered the basics of Internationalization and the
API used to localize different parts of your application. The next
section deals with applying this knowledge to internationalizing your
web application.

8.3[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Internationalization
and the web tier

In the previous section you saw what internationalization is and how to
write programs to localize applications. Now, let us move on to applying
this knowledge to web applications.

Internationalizing the web tier uses all the concepts explained earlier
in this chapter. Additionally, it uses time tested frameworks and tag
libraries to incorporate the actual implementation details. Also
mentioned is a new Internationalization Service that aims to standardize
J2EE internationalization. Here are some of the commonly used techniques
to internationalize a web application:

[      ]{style=""}

1.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Struts
Internationalization

2.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}JSTL
tags for Internationalization

3.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Java
Server Faces Internationalization

4.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Localizing
Tiles

5.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}The
J2EE Internationalization Service (JSR 150)

 

19.3.1 Struts Internationalization

[      ]{style=""}The Struts application development framework provides
a simple API for internationalization. It builds upon the
internationalization functionality provided by Java for building
internationalized and localized applications.

[      ]{style=""}Though the API is simple and allows us to quickly
localize an application, the internationalization support in Struts
applications is limited to the presentation of text and images only. It
does not support locale specific input methods used with languages like
Korean and Japanese, depending on the browser to handle these instead.

 

In general, Struts applications deal with internationalization in the
following way:

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}The
application developer creates several properties files (one per locale)
that contain the localized strings for messages to be displayed to the
user.

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}The
Struts controller servlet is configured to look up information from
these properties files.

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}When
the Struts controller servlet receives a request, it checks the user's
locale and looks up a resource bundle confirming to that locale and
displays the appropriate localized messages.

[      ]{style=""}

Figure 19.4 shows the classes in the Struts I18n API. Some of the key
concepts in the Struts Internationalization API are:

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}[Locale]{style="font-size: 10pt; font-family: Courier;"}
-- The
[java.util.Locale]{style="font-size: 10pt; font-family: Courier;"} class
is explained in section 19.1.4

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}[ResourceBundle]{style="font-size: 10pt; font-family: Courier;"}
-- The [ResourceBundle]{style="font-size: 10pt; font-family: Courier;"}
class is explained in section 19.1.4

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}[PropertyResourceBundle]{style="font-size: 10pt; font-family: Courier;"}
-- This implementation of the ResourceBundle class allows you to define
resources in the "key=value" format. [   ]{style=""}The text to be
localized is saved in a Java properties file.

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}[MessageFormat]{style="font-size: 10pt; font-family: Courier;"}
-- The [MessageFormat]{style="font-size: 10pt; font-family: Courier;"}
class is explained in section 19.1.4

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}[MessageResources]{style="font-size: 10pt; font-family: Courier;"}
-- The
[org.apache.struts.util.MessageResources]{style="font-size: 10pt; font-family: Courier;"}
class behaves like a resource bundle against which you can query in
order to get the value of a string for a given locale.

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}MessageTag
-- Custom tag that retrieves an internationalized message string from
the
[ActionResources]{style="font-size: 10pt; font-family: \"Courier New\";"}
object stored as a context attribute by the associated
[ActionServlet]{style="font-size: 10pt; font-family: \"Courier New\";"}
implementation.

 

![](Ch19-I18N_and_L10N_files/image008.jpg){v:shapes="_x0000_s1164"
height="101" width="510"} 

 

 

 

 

\

Figure 19.4 Some of the I18n classes provided by the Struts framework

 

[      ]{style=""}Let us see how you can internationalize an application
using Struts. Consider the ABC Bank web application explained in Chapter
5. For simplicity, only two JSP pages, index.jsp and main.jsp are shown.
In index.jsp (Figure 19.5), you will be able to pick a specific locale,
and main.jsp (Figure 19.6) will display the main page for the ABC Bank
web application in the language selected.

[![](Ch19-I18N_and_L10N_files/image010.jpg){v:shapes="_x0000_s1161"
height="140"
width="624"}]{style="position: relative; z-index: 4; left: -7px; top: 17px; width: 624px; height: 157px;"} 

 

 

 

 

 

 

 

 

 

 

 

\

Figure 19.5 index.jsp showing the languages supported

 

 

Listing 19.7 shows the code for index.jsp. This page contains a combo
box that allows the user to select a particular language. When the user
selects it, main.jsp is invoked with a request parameter for the
language selected. For example, when the user selects French, main.jsp
is invoked with a request parameter of "language=fr".

 

Listing 19.7 index.jsp

\<HTML\>

...

\<BODY\>

...

\<center\>

\<h3\> Select the locale of your choice \</h3\>

\<form name=\"localeForm\"\>

\<select name=\"myLocales\"

OnChange=

\"location.href=localeForm.myLocales.options\[selectedIndex\].value\"\>

[     ]{style=""}\<option selected\>Please Select Locale

[     ]{style=""}\<option value=\"main.jsp?language=en-US\"\>US English

[     ]{style=""}\<option value=\"main.jsp?language=fr\"\>French

\</select\>

\</form\>

...

\</BODY\>

\</HTML\>

 

 

 

 

 

 

 

 

 

[[![](Ch19-I18N_and_L10N_files/image012.jpg){v:shapes="_x0000_s1162"
height="178"
width="623"}]{style="position: absolute; left: -7px; top: -35px; width: 623px; height: 178px;"}]{style="position: relative; z-index: 5;"} 

 

 

 

 

 

 

 

 

 

 

\

Figure 19.6 The main page is displayed in French when the user selects
French in index.jsp

 

Listing 19.8 main.jsp

\<%@ page language=\"java\" %\>

\<%@page import=\"org.apache.struts.action.Action\"%\>

\<%@ taglib uri=\"/WEB-INF/struts-tiles.tld\" prefix=\"tiles\" %\>

 

\<%

[  ]{style=""}java.util.Locale newLocale = null;

[  ]{style=""}String language = request.getParameter(\"language\");[ 
]{style=""}\|#1

 

[  ]{style=""}if(language.equals(\"fr\")) {[                   
]{style=""}

[ ]{style=""}[  ]{style=""}[ ]{style=""}newLocale = new
java.util.Locale( \"fr\" );[   ]{style=""}\|#2

[   ]{style=""}[ ]{style=""}session.setAttribute( Action.LOCALE_KEY,
newLocale ); \|#3

[  ]{style=""}}

[  ]{style=""}else {

[ ]{style=""}[  ]{style=""}[ ]{style=""}newLocale = new
java.util.Locale( \"en\",\"US\" ); \|#2

[   ]{style=""}[ ]{style=""}session.setAttribute( Action.LOCALE_KEY,
newLocale ); \|#3

[  ]{style=""}}[   ]{style=""}

%\>[ ]{style=""}

\<tiles:insert definition=\"doc.mainLayout\" flush=\"true\" /\>

 

(annotation)\< #1[  ]{style=""}Get the user's language preference from
the request\>

(annotation)\< #2[  ]{style=""}Based on the language chosen, create the
appropriate locale instance\>

(annotation)\< #2 Set the locale in the session\>

 

 

In Listing 19.8, main.jsp gets the user's preferred language from the
request parameter as shown by:

[  ]{style=""}String language = request.getParameter(\"language\");

 

Next, it checks whether the language is French ("fr"), creates the
appropriate locale object and initializes the session attribute
Action.LOCALE_KEY with this locale as shown by:

[  ]{style=""}if(language.equals(\"fr\")) {

[ ]{style=""}[  ]{style=""}newLocale = new java.util.Locale( \"fr\" );

[   ]{style=""}session.setAttribute( Action.LOCALE_KEY, newLocale );

[  ]{style=""}}

Similarly, if the language is English then the above steps are repeated
for that locale.

 

Finally, the appropriate tiles definition to load the main page of the
ABC Bank application is invoked using:

[  ]{style=""}\<tiles:insert definition=\"doc.mainLayout\"
flush=\"true\" /\>

In order to understand the working of a Struts-Tiles application, please
refer to Chapter 5.

 

[Note:]{.underline} In Struts based applications, once the locale is
chosen by the user, it is saved in a session attribute called
[[org.apache.struts.action.Action.LOCALE_KEY]{style="font-family: Courier;"}]{.codeChar4}.
Once the locale is saved, all the JSP pages that use locale specific
data, lookup this attribute and display localized messages accordingly.

[      ]{style=""}In figure 19.6 you saw the main page of the ABC Bank
web application localized for French. This page contains the header, a
menu showing two options an empty body and a footer giving contact
information.

[      ]{style=""}Let us see how header.jsp managed to get the heading
in French. The code used to get the heading in header.jsp is very simple
and is shown in Listing 19.9

 

Listing 19.9 header.jsp

\<%@ page contentType=\"text/html;charset=UTF-8\" language=\"java\" %\>

\<%@ taglib uri=\"/WEB-INF/struts-bean.tld\" prefix=\"bean\" %\> \|#1

 

\<table bgcolor=\"#d0d0d0\" cellspacing=\"0\" cellpadding=\"5\"
border=\"0\"

[       ]{style=""}width=\"100%\"\>

[ ]{style=""}\<tr\>

[   ]{style=""}\<td\>

[   ]{style=""}[ ]{style=""}\<center\> \<h2\> \<bean:message
key=\"header.title\"/\> \</h2\> \<br\> \|#2

[   ]{style=""}\</td\>

[ ]{style=""}\</tr\>

\</table\>

 

(annotation)\< #1[  ]{style=""}Declare the struts-bean tag library\>

(annotation)\< #2[  ]{style=""}Use the \<bean:message\> tag to extract
the header from the resource bundle for a given locale\>

 

You might wonder where the actual header comes from. When a locale of
"fr" is chosen in index.jsp the header magically appears in French!

[      ]{style=""}Earlier in this section, we had mentioned that the
org.apache.struts.util.MessageResources class is used to look up
resource bundles for locale specific information. This class is declared
in the struts configuration file (/WEB-INF/struts-config.xml) as shown:

[  ]{style=""}\<message-resources
parameter=\"com.abcbank.example.ApplicationResources\"/\>

 

By declaring the MessageResources entry in struts-config.xml, we specify
that the class specified by the attribute "parameter" will be looked up
for any locale sensitive messages. In this case, a class called
[[com.abcbank.example.ApplicationResources]{style="font-family: Courier;"}]{.codeChar4}
or a properties file called ApplicationResources.properties in the
com.abcbank.example folder is looked up.[[
]{style="font-family: Courier;"}]{.codeChar4}

[[[   ]{style=""}]{style="font-family: Courier;"}]{.codeChar4}

[[If a language of "fr" had been specified, a properties file called
ApplicationResources_fr.properties would be looked up. This file has the
following entry:]{style=""}]{.codeChar4}

[   ]{style=""}header.title=Banque de ABC

 

 

In this section we saw how Struts applications can be internationalized
and localized. One important point to keep in mind is that in addition
to localizing text messages, care should be given to ensure that even
the exception details (error messages) are localized. Of course, this is
done in a similar fashion as an ordinary text message.

For example, ApplicationResources.properties can have an entry:

[   ]{style=""}error.firstname.required=First Name is required

 

ApplicationResources_fr.properties would have an entry:

[   ]{style=""}error.firstname.required=Le prénom est exigé

 

As in any regular Struts application, an ActionError is created for a
validation error in the validate method of the ActionForm class. Struts
automatically checks the default locale in the session and accesses the
right resource bundle to extract the localized error message. Further,
if any parameters need to be passed in dynamically, the ActionError
class has constructors that take the key and an array of strings
containing the replacement parameters to be used in the validation error
messages.[  ]{style=""}Some of the commonly used constructors are:

ActionError(String key)

ActionError(String key, Object value)

 

ActionError(String key, Object values\[\])

 

Figure 19.7 shows the error messages displayed in French for the
firstName, lastName and monthly salary fields

 

 

 

[[![](Ch19-I18N_and_L10N_files/image014.jpg){v:shapes="_x0000_s1184"
height="204"
width="336"}]{style="position: absolute; left: 149px; top: -24px; width: 336px; height: 204px;"}]{style="position: relative; z-index: 6;"} 

 

 

 

 

 

 

 

 

 

\

Figure 19.7 Struts form showing localized validation error messages

 

19.3.2 JSTL tags for Internationalization

JSTL provides an Internationalization API to localize text messages and
images. In a web application the user specifies a locale, which is used
throughout the application, and the appropriate messages are displayed
to the user.

[      ]{style=""}Let us take an example of the ABC Bank web application
to see how to use the JSTL tags for Internationalization. There is a
simple rule that needs to be followed when internationalizing your web
application: Always display to the user the set of locales and languages
supported by your application. That way, when the user enters your
application, she has a choice of languages to view the content in. Only
offer those choices for which you have localized content. We will see
how this rule is followed; in case of the ABC Bank web application.

[      ]{style=""}When the user visits the first page (index.jsp) she
will see a page similar to the one shown in figure 19.8.[ 
]{style=""}This page shows the languages supported as US English and
French only. There is a third option of selecting the user's Browser
default if either of the two is not preferred. But please note, that
only US English and French are supported in this case.

 

[![](Ch19-I18N_and_L10N_files/image016.gif){v:shapes="_x0000_s1156"
height="144"
width="623"}]{style="position: relative; z-index: 7; left: -7px; top: 3px; width: 623px; height: 147px;"} 

 

 

*[ ]{style="font-size: 16pt;"}*

*[ ]{style="font-size: 16pt;"}*

 

 

 

\

Figure 19.8 index.jsp showing the languages supported

 

The code for index.jsp (Listing 19.9) is quite simple. When the user
selects a particular language, say US English, the locale for that
language (en_US) is set in the session and the control passes to a page
called "main.jsp".

 

Listing 19.9 index.jsp

\<%@ page language=\"java\" %\>

\<%@ page import=\"java.util.Locale\" %\>

\<%

[  ]{style=""}[String lang =
request.getParameter(\"language\");]{style=""}**[   ]{style=""}**\|#1

[  ]{style=""}if ( \"en-US\".equals(lang) ) {

[   
]{style=""}[session.setAttribute(\"userLocale\",Locale.US);]{style=""}**[  
]{style=""}**\|#2

[    ]{style=""}[response.sendRedirect(\"main.jsp\");
]{style=""}**[             ]{style=""}**\|#3

[    ]{style=""}return;

[  ]{style=""}}

[  ]{style=""}else if ( \"fr\".equals(lang) ) {

[    ]{style=""}session.setAttribute(\"userLocale\",Locale.FRENCH);

[    ]{style=""}response.sendRedirect(\"main.jsp\");

[    ]{style=""}return;

[  ]{style=""}}

[  ]{style=""}else if ( \"browser\".equals(lang) ) {

[    ]{style=""}session.removeAttribute(\"userLocale\");

[    ]{style=""}response.sendRedirect(\"main.jsp\");

[    ]{style=""}return;

[  ]{style=""}}

%\>

\<HTML\>

\<HEAD\>

[  ]{style=""}\<TITLE\>Examples of JSTL I18n Custom Tag Library
Usage\</TITLE\>

\</HEAD\>

\<BODY\>

\<center\> \<h2\> Welcome to the ABC Bank web application \</h2\>
\</center\>\<hr/\>

 

\<center\>

Please select one of the following locales:\<br\>

(**\<**[a href=\"index.jsp?language=en-US]{style=""}**\"\>**US
English\</a\>)\<br\>

(\<a href=\"index.jsp?language=fr\"\>French\</a\>)\<br\>

(\<a href=\"index.jsp?language=browser\"\>Browser Default\</a\>)\<br\>

\<hr/\>\<p/\>

\</center\>

 

\</BODY\>

\</HTML\>

(annotation)\< #1[  ]{style=""}Get the user's language preference from
the request\>

(annotation)\< #2 Set the appropriate locale in the session\>

(annotation)\< #3 Redirect the flow to main.jsp\>

 

In chapter 5 you saw how to create a web application using Struts and
Tiles. Please refer to chapter 5 to see how the tiles definition is
mapped to a layout page containing the various JSP pages that make up
the ABC Bank web application. In this example, main.jsp just has a tiles
definition that indicates the layout that needs to be loaded. Listing
19.10 shows main.jsp

 

Listing 19.10 main.jsp

\<%@ page language=\"java\" %\>

\<%@ taglib uri=\"/WEB-INF/struts-tiles.tld\" prefix=\"tiles\" %\>

 

\<tiles:insert definition=\"doc.mainLayout\" flush=\"true\" /\>

[      ]{style=""}[ ]{style=""}

If US English was chosen as the locale, the following page would be
displayed as shown in Figure 19.9.

 

 

[[![](Ch19-I18N_and_L10N_files/image018.gif){v:shapes="_x0000_s1157"
height="178"
width="623"}]{style="position: absolute; left: -7px; top: -24px; width: 623px; height: 178px;"}]{style="position: relative; z-index: 8;"} 

 

 

 

 

 

 

 

 

 

\

Figure 19.9 The main page is displayed in English when the user selects
US English in index.jsp

 

In Figure 19.9 the main page is displayed with all the messages
displayed in English. Of course, we are used to seeing web pages in
English and this might not appear to be much of a deal. But in the
background, there is a certain amount of complexity that is involved in
displaying the information in a particular language. Let us see how this
works. When the tiles definition for "doc.mainLayout" is loaded, a page
called "default_layout.jsp" is loaded which has links to the various
tiles definitions for header, menu, body and footer. Figure 19.10 shows
the layout of the page. In this particular case, as this is the main
screen displayed, and as the user has not selected any menu option yet,
no body will be displayed.

 

[ ]{style=""}

  -- ----------------------------------------------------------------------------------------------
     
     ![](Ch19-I18N_and_L10N_files/image020.gif){v:shapes="_x0000_s1159" height="230" width="177"}
  -- ----------------------------------------------------------------------------------------------

 

 

 

 

 

 

 

 

 

 

 

 

 

 

\

Figure 19.10[  ]{style=""}default_layout.jsp showing the header, menu,
body and footer for the ABC Bank web application.

 

Let us see the header.jsp to understand how the messages were localized.
Listing 19.11 shows header.jsp

 

Listing 19.11 header.jsp

 

\<%@ page contentType=\"text/html;charset=UTF-8\" language=\"java\" %\>

**\<%@** taglib prefix=\"fmt\"
uri=\"http://java.sun.com/jsp/jstl/fmt**\" %\>** \|#1

 

**\<%@** include file=\"./declarebundle.jsp\" **%\>[   ]{style=""}**\|#2

 

\<table bgcolor=\"#d0d0d0\" cellspacing=\"0\" cellpadding=\"5\"
border=\"0\"

[       ]{style=""}width=\"100%\"\>

\<tr\>

[  ]{style=""}\<td\>

[  ]{style=""}\<center\> \<h2\>

**[   ]{style=""}\<**fmt:setLocale value=\"\<%=userLocale%\>\"/**\>**
\|#3

**[   ]{style=""}\<**fmt:bundle
basename=\"com.abcbank.example.ApplicationResources**\"\>** \|#4

**[   ]{style=""}[  ]{style=""}\<**fmt:message key=\"header.title\"/\>
\|#5

[   ]{style=""}\</fmt:bundle\>

[   ]{style=""}\</h2\> \<br\>

[  ]{style=""}\</td\>

\</tr\>

\</table\>

 

(annotation)\< #1[  ]{style=""}Declare the[  ]{style=""}JSTL
internationalization tag library \>

(annotation)\< #2 Include the resourcebundle.jsp file to get the user's
choice of locale\>

(annotation)\< #3 Set the locale for the application with the user's
choice\>

(annotation)\< #4 Declare a resource bundle to be used by the
application\>

(annotation)\< #5 Get the header using the "header.title" key[ 
]{style=""}from the resource bundle\>

 

 

 

Listing 19.9 shows the source for header.jsp. There are three important
points, which will be common in all the JSP pages that will use the JSTL
internationalization tags:

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}Declaring
the JSTL Internationalization tag library

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}Including
the "declareBundle.jsp" file

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}Using
the \<fmt\> tag to declare a resource bundle and access its contents

[      ]{style=""}You will first declare the tag library that contains
the internationalization specific tags. Next you include a JSP file
called "declareBundle.jsp" that will get the user specified locale from
the session. This locale will be used by header.jsp in order to extract
the header from the appropriate resource bundle.

 

Listing 19.12 declareBundle.jsp is used to get the user specified locale
from the session

 

\<%@ page import=\"java.util.Locale\" %\>

\<% Locale userLocale = (Locale)
session.getAttribute(\"userLocale\");%\>

 

Listing 19.12 shows declareBundle.jsp. The code is quite simple. All
this JSP does is to get the current locale from the session.

 

Coming back to header.jsp, you have declared the tag library and you
have obtained the user specified locale. Now the only task remaining is
to display the header to the user in the chosen language, English in
this case. In order to do this, you will have to use the JSTL \<fmt\>
tag.

You first set the locale using the \<fmt:setLocale\> tag. The code to do
this looks like:

[  ]{style=""}\<fmt:setLocale value=\"\<%=userLocale%\>\"/\>

 

Next, you declare the resource bundle to be used for this locale. The
code looks like:

[  ]{style=""}\<fmt:bundle
basename=\"com.abcbank.example.ApplicationResources\"\>

[   ]{style=""}..

[  ]{style=""}\</fmt:bundle\>

In this code snippet, you declare a resource bundle using the
\<fmt:bundle\> tag. This tag takes an attribute called "basename" which
indicates the name of the class containing the locale specific
information or the name of the java properties file which contains this
information. In this case, the resource bundle is called
ApplicationResources and is located in the "com.abcbank.example"
package.

 

Finally, having declared the appropriate resource bundle to be looked
up, you use the \<fmt:message\> tag to look up the locale specific value
for a given string as:

[  ]{style=""}\<fmt:message key=\"header.title\"/\>

Here, the resource bundle ApplicationResources.properties is looked up
for a string matching the key "header.title" and it's value, "ABC Bank"
is retrieved and displayed to the user.

 

The entry for "header.title" in ApplicationResources.properties would
look like:

[  ]{style=""}header.title=ABC Bank

 

That's it! You have just seen how the JSTL Internationalization tags can
be used to display localized messages. Here, header.jsp was customized
to display the localized strings for each message that the user would
see. Similarly, the footer and the menu also use the Internationalzation
tags to display the messages. Of course, what you have seen is what the
page would look like if the user had selected "US English". What if the
user had selected "French" as the preferred locale? In that case, the
main page would look like the page shown in Figure 19.11

 

 

[[![](Ch19-I18N_and_L10N_files/image022.gif){v:shapes="_x0000_s1158"
height="185"
width="623"}]{style="position: absolute; left: 5px; top: -24px; width: 623px; height: 185px;"}]{style="position: relative; z-index: 10;"} 

 

 

 

 

 

 

\

[            ]{style=""}

Figure 19.11 The main page is displayed in French when the user selects
French in index.jsp

Figure 19.11 shows the main page with all the required messages
displayed in French. Just to get a better idea of what the other two JSP
pages look like, Listing 19.13 and Listing 19.14 show the relevant parts
of the source for menu.jsp and footer.jsp respectively.

 

Listing 19.13 menu.jsp

 

\...

\<%@ include file=\"./declarebundle.jsp\" %\>

 

\<fmt:setLocale value=\"\<%=userLocale%\>\"/\>

\...

\<fmt:bundle basename=\"com.abcbank.example.ApplicationResources\"\>

 

[   ]{style=""}\<li\>

[    ]{style=""}\<html:link [ ]{style=""}page=\"/customerDetails.do\"\>

[      ]{style=""}\<fmt:message key=\"menu.customerDetails\"/\>

[    ]{style=""}\</html:link\>

[   ]{style=""}\</li\>

 

\<li\>

[ ]{style=""}\<html:link page=\"/logoutMessage.do\"\>

**[   ]{style=""}**\<fmt:message key=\"menu.logout\"/\>[                
]{style=""}

[ ]{style=""}\</html:link\>

[   ]{style=""}\</li\>

 

\</fmt:bundle\>

 

 

 

Listing 19.14 footer.jsp

[   ]{style=""}. . .

[ ]{style=""}\<%@page import=\"java.util.Date\"%\>

[ ]{style=""}\<% Date now = new Date(); %\>

[ ]{style=""}\<fmt:setLocale value=\"\<%=userLocale%\>\"/\>

[ ]{style=""}\<fmt:bundle
basename=\"com.abcbank.example.ApplicationResources\"\>

[    ]{style=""}\<fmt:message key=\"footer.question\"/\>

[    ]{style=""}\<fmt:message key=\"footer.contact\"/\>[  ]{style=""}

[    ]{style=""}\<fmt:formatDate value=\"\<%=now%\>\"
dateStyle=\"full\"/\>

[    ]{style=""}\<fmt:formatDate value=\"\<%=now%\>\"
type=\"time\"/\>[    ]{style=""}

[ ]{style=""}\</fmt:bundle\>

 

In Listing 19.14 you will see that in addition to the \<fmt:message\>
tag, the \<fmt:formatDate\> tag is also used. This tag is used to format
the date and time for a given locale. To see how the dates and times
appear for English and French locales, see the footer in figures 19.9
and 19.11 respectively.

 

19.3.3 Java Server Faces Internationalization

Java Server Faces provides a simple mechanism for internationalizing web
applications. Using this mechanism you can localize static data, dynamic
data and text messages. To localize static data, JSF uses the JSTL
Internationalization tags that were explained in Section 19.2.2. Dynamic
data is available only at run time and internationalizing dynamic data
is a model bean function.

[            ]{style=""}In this section you will see how to localize
static data, dynamic data and text messages. It achieves this by
extensively using JSTL Internationalization tags. Consider the JSP page
that we had introduced in chapter 5, customerDetails.jsp. This JSP page
contains customer information like first name, last name, contact
details etc. In the previous examples you had seen this page in the
context of a Struts-Tiles-JSF application. Here we will just consider
the single JSP and localize it using JSTL tags for JSF.

Let us take another look at index.jsp shown in Figure 19.12.

** **

** **

[[![](Ch19-I18N_and_L10N_files/image023.gif){v:shapes="_x0000_s1174"
height="144"
width="623"}]{style="position: absolute; left: 5px; top: -11px; width: 623px; height: 144px;"}]{style="position: relative; z-index: 11;"}** **

\

[ ]{style=""}

 

 

 

 

 

 

Figure 19.12 The main page is displayed in French when the user selects
French in index.jsp

You saw this page in section on JSTL tags. Three locales are presented
to the user: US English and French and a default locale. When a link is
clicked, control transfers to customerDetails.jsp. Listing 19.15 shows
the code for index.jsp

 

Listing 19.15 index.jsp

\<%@ page language=\"java\" %\>

\<%@ page import=\"java.util.Locale\" %\>

\<%

[  ]{style=""}[String lang =
request.getParameter(\"language\");]{style=""}**[   ]{style=""}**\|#1

[  ]{style=""}if ( \"en-US\".equals(lang) ) {

[   
]{style=""}[session.setAttribute(\"userLocale\",Locale.US);]{style=""}**[  
]{style=""}**\|#2

[   
]{style=""}**response.sendRedirect(\"/faces/customerDetails.jsp\");[ 
]{style=""}**\|#3

[    ]{style=""}return;

[  ]{style=""}}

...

%\>

...

\<center\>

Please select one of the following locales:\<br\>

(**\<**[a href=\"index.jsp?language=en-US]{style=""}**\"\>**US
English\</a\>)\<br\>

(\<a href=\"index.jsp?language=fr\"\>French\</a\>)\<br\>

(\<a href=\"index.jsp?language=browser\"\>Browser Default\</a\>)\<br\>

\<hr/\>\<p/\>

\</center\>

\</BODY\>

\</HTML\>

(annotation)\< #1[  ]{style=""}Get the user's language preference from
the request\>

(annotation)\< #2 Set the appropriate locale in the session\>

(annotation)\< #3 Redirect the flow to customerDetail.jsp\>

 

If French were selected as the preferred locale, then you would see the
following output as shown in Figure 19.13. In this page, we use JSTL
tags to display localized messages. These messages represent the labels
for the text fields.

[ ]{style=""}

  -- ----------------------------------------------------------------------------------------------
     
     ![](Ch19-I18N_and_L10N_files/image025.jpg){v:shapes="_x0000_s1181" height="300" width="513"}
  -- ----------------------------------------------------------------------------------------------

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

\

Figure 19.13 customerDetails.jsp when French is selected as the
preferred locale

 

The source for customerDetails.jsp is shown in Listing 19.16.

Listing 19.16 customerDetails.jsp

 

\<%@ page contentType=\"text/html;charset=UTF-8\" language=\"java\"
%\>\|#1

\<%@ taglib prefix=\"fmt\" uri=\"http://java.sun.com/jsp/jstl/fmt\" %\>

\<%@ taglib uri=\"http://java.sun.com/jsf/html\" prefix=\"h\" %\>

\<%@ taglib uri=\"http://java.sun.com/jsf/core\" prefix=\"f\" %\>

 

\<% java.util.Locale userLocale = (java.util.Locale)
session.getAttribute(\"userLocale\");%\>[                
]{style=""}\|#2

 

\<body\>

\<center\>

\<f:use_faces\>

\<h:form id=\"cForm\" formName=\"cForm\"\>

\<fmt:setLocale value=\"\<%=userLocale%\>\"/\>[    ]{style=""}\|#3

\<fmt:bundle basename=\"com.abcbank.example.ApplicationResources\"\>[ 
]{style=""}\|#4[   ]{style=""}

 

\<fmt:message key=\"customer.firstName\" /\> \|#5

\<h:input_text id=\"firstName\" valueRef=\"CustomerForm.firstName\" /\>

\<br\>

\<fmt:message key=\"customer.lastName\" /\> \|#5

\<h:input_text id=\"lastName\" valueRef=\"CustomerForm.lastName\" /\>

\<br\>

\<!\-- Rest of the fields in the form \--\>

...

\<h:command_button id=\"submit\" action=\"success\" key=\"submit\"
commandName=\"submit\" label=\"Submit\" /\>

\<h:command_button id=\"reset\" type=\"RESET\" commandName=\"reset\"

label=\"Reset\" /\>

\</fmt:bundle\>[     ]{style=""}

\</h:form\>

\</center\>

 

\</f:use_faces\>

 

(annotation)\< #1[  ]{style=""}Declare the page's character encoding to
be UTF-8\>

(annotation)\< #2 Get the preferred locale from the session\>

(annotation)\< #3 Set the locale using the \<fmt:setLocale\> tag\>

(annotation)\< #4 Declare the resource bundle using the \<fmt:bundle\>
tag\>

(annotation)\< #5 Display localized messages from the resource bundle
using the \<fmt:message\> tag\>

 

19.3.4 Localizing Tiles

In Chapter 5 you saw how to use Tiles to organize your JSP pages. The
Tiles framework provides an easy way to add tiles or templates to a JSP
page to present content in a dynamic fashion.

[      ]{style=""}The Tiles framework, just like Struts can be localized
to provide different tiles based on a user's preferred locale. For
example, the header tile that we saw in the ABC Bank web application
example in Chapter 5 could be replaced with a different header that
corresponds to a specific locale. It could contain an area-specific flag
for instance or simply a different background color.

[      ]{style=""}A Tiles application has a Tiles definition file
(example:/WEB-INF/tiles_definition.xml) that defines the structure of a
JSP page using various tiles, for the header, menu, body, footer etc. In
the case of a localized Tiles application, there will one such file *per
locale* along with the default tiles_definition.xml file. For example,
if your application supports US English and French, there will be two
definition files, one for each locale as well as a default one:

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}tiles_definition_fr.xml

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}tiles_definition_en.xml

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}tiles_definition.xml

[Note:]{.underline} The naming conventions for the Tiles definition
files are the same as for a java.util.ResourceBundle class as explained
earlier in section 19.1.

[      ]{style=""}Again, just as in a localized Struts application, the
session attribute Action.LOCALE_KEY is looked up for a user's preferred
or default locale and the appropriate definition file is loaded.

For example, if your original file definition is shown in Listing 19.17.

 

Listing 19.17 tiles_definitions.xml

\<tiles-definitions\>

[  ]{style=""}\<definition name=\"foo.bar\" path=\"ABCBankLayout.jsp\"\>

[   ]{style=""}[  ]{style=""}\<put name=\"title\"[ 
]{style=""}value=\"My ABC Bank example\" /\>

[   ]{style=""}[  ]{style=""}\<put name=\"header\" value=\"/header.jsp\"
/\>

[   ]{style=""}[  ]{style=""}\<put name=\"menu\"[  
]{style=""}value=\"/menu.jsp\" /\>

[   ]{style=""}[  ]{style=""}\<put name=\"footer\" value=\"/footer.jsp\"
/\>

[   ]{style=""}[  ]{style=""}\<put name=\"body\"[  
]{style=""}value=\"/body.jsp\" /\>

[  ]{style=""}\</definition\>

\</tiles-definitions\>

 

 

The localized Tiles definition file for French is shown in Listing 19.18

 

Listing 19.18 tiles_definitions_fr.xml

\<tiles-definitions\>

[  ]{style=""}\<definition name=\"foo.bar\" path=\"ABCBankLayout.jsp\"\>

[   ]{style=""}[  ]{style=""}\<put name=\"title\"[ 
]{style=""}value=\"Mon exemple de banque de ABC\"/\>

[   ]{style=""}[  ]{style=""}\<put name=\"header\"
value=\"/fr/header.jsp\" /\>

[   ]{style=""}[  ]{style=""}\<put name=\"menu\"[  
]{style=""}value=\"/fr/menu.jsp\" /\>

[   ]{style=""}[  ]{style=""}\<put name=\"footer\"
value=\"/fr/footer.jsp\" /\>

[   ]{style=""}[  ]{style=""}\<put name=\"body\"[  
]{style=""}value=\"/fr/body.jsp\" /\>

[  ]{style=""}\</definition\>

\</tiles-definitions\>

 

In this section you saw how to localize Tiles. The important thing to
note here is that localizing Tiles layouts is just one part of
localizing your application. The actual meat of the localization still
lies in localizing text messages, labels and images. A combination of
Struts localization and Tiles localization can make your application
very dynamic and enable supporting multiples locales a painless process.
On the flip side, however, the approach of localizing tiles can end up
in multiple copies of JSP pages which can become quite cumbersome to
maintain as the application size grows.

 

19.3.5 Processing localized input

In the previous section you saw how to internationalize a JSF
application and how easy it is to present locale specific information to
a user with JSTL tags. In this section you will see how to process
*localized input* in your web application. Localized input is data input
in a native language using locale specific formats. This section
attempts to answer the following question: How does your back-end java
code process data input in a native language?

[      ]{style=""}There are various approaches to do this. You can try
to process localized data in a Struts based application or you can
process localized input in a JSF application. There are other approaches
too but we will only see these two, as these are the two most common
approaches in web tier internationalization.

**[ ]{.underline}**

Struts approach to processing localized input:

Section 19.2.1 showed a simple example to internationalize a web
application. In that example, when a user entered the web application,
she chose a preferred locale, which was set in the session and every
page in the application used this locale to format data and display it
to the user in a localized fashion. That was easy, wasn't it?

[      ]{style=""}Let us consider a simple form with two fields,
fullName and monthlySalary. This form is shown in figure 19.14.

[ ]{style=""}

  -- ---------------------------------------------------------------------------------------------
     
     ![](Ch19-I18N_and_L10N_files/image027.jpg){v:shapes="_x0000_s1191" height="94" width="225"}
  -- ---------------------------------------------------------------------------------------------

 

 

 

 

 

 

\

Figure 19.14 Form showing name and salary
fields[[]{style="font-weight: normal;"}]{.underline}

In this case, the form, let's call it CustomerForm is shown in Listing
19.19.

 

Listing 19.19 CustomerForm.java

public class CustomerForm extends ActionForm {

[   ]{style=""}private String fullName = null;

[   ]{style=""}private double monthlySalary = 0.0;

\...

}

John Doe enters his monthly salary as 5431.52 and submits the form.
That's it, the form fields are populated nicely and the application
works without a hitch. The conversion of the monthly salary from a
String to a double is automatically taken care of by Struts and John Doe
won't have any problems with the application.

[      ]{style=""}Now, if the same application is viewed by a user in
France and he decides to enter the same amount in the French format as 5
431,52 what will happen?

[      ]{style=""}When you submit the application, the monthlySalary
attribute in CustomerForm ends up being populated with 0.0 instead of
5431.52. This is because, when the form is submitted, the String value
"5 431,52" is passed by the
[org.apache.struts.util.RequestUtils]{style="font-size: 10pt; font-family: Courier;"}
class to the
[org.apache.commons.beanutils.BeanUtils]{style="font-size: 10pt; font-family: Courier;"}
class's [populate]{style="font-size: 10pt; font-family: Courier;"}
method as shown in the following code snippet from RequestUtils:

 

Listing 19.20 populate method in org.apache.struts.util.RequestUtils

[public static void
populate(]{style="font-size: 10pt; font-family: Courier;"}

[Object bean,]{style="font-size: 10pt; font-family: Courier;"}

[String prefix,]{style="font-size: 10pt; font-family: Courier;"}

[String suffix,]{style="font-size: 10pt; font-family: Courier;"}

[HttpServletRequest
request)]{style="font-size: 10pt; font-family: Courier;"}

[throws ServletException
{]{style="font-size: 10pt; font-family: Courier;"}

[[   ]{style=""}]{style="font-size: 10pt; font-family: Courier;"}

[// extract field values from the
JSP]{style="font-size: 10pt; font-family: Courier;"}

[// and Set the corresponding properties of our
bean]{style="font-size: 10pt; font-family: Courier;"}

[try {]{style="font-size: 10pt; font-family: Courier;"}

[[    ]{style=""}**BeanUtils.populate(bean,
properties);**]{style="font-size: 10pt; font-family: Courier;"}

[} catch (Exception e)
{]{style="font-size: 10pt; font-family: Courier;"}

[[    ]{style=""}throw new ServletException(\"BeanUtils.populate\",
e);]{style="font-size: 10pt; font-family: Courier;"}

[}]{style="font-size: 10pt; font-family: Courier;"}

Here, [properties]{style="font-size: 10pt; font-family: Courier;"} is an
[HashMap]{style="font-size: 10pt; font-family: Courier;"} containing the
names of the fields and the values obtained from the JSP page. What ends
up happening is that the value "5 431,52" is applied to the double value
of monthlySalary. This throws an exception, which is hidden from the
user, resulting in a default value of 0.0 being populated in the
[monthlySalary]{style="font-size: 10pt; font-family: Courier;"} field.

[      ]{style=""}What is the solution then? How do we make our Struts
applications process localized input?

Unfortunately, as the
[BeanUtils]{style="font-size: 10pt; font-family: Courier;"} class does
not check the locale at the time of populating the form, a way out of
this situation is to make the
[monthlySalary]{style="font-size: 10pt; font-family: Courier;"} field a
[String]{style="font-size: 10pt; font-family: Courier;"} instead of a
[double]{style="font-size: 10pt; font-family: Courier;"}. When this form
attribute has to be used, a customized routine will have to be written
to convert the localized String into a double.

JSF approach to processing localized input:

In the previous section you saw how Struts handles internationalization
and the problems with trying to process localized input. In this section
you will see how to handle the same situation with a pure JSF form.

[      ]{style=""}In JSF applications, the JSF implementation
automatically converts data between the model views and the presentation
views. For example, if a form has a text field for the date of birth and
this field is represented as a java.util.Date in the form bean, the
implementation converts the values automatically if a Date renderer is
specified.

[      ]{style=""}However, there might be cases where you might want to
convert data from one type into a different type, between the model and
presentation views. In such cases, JSF provides standard classes called
Converters, which will do the conversion for you. If further
customization is required for conversions and the standard JSF
converters don't support this, then you can create your own converters
very easily.

[      ]{style=""}In this section we will see how to use Converters that
provide localization services. Figure 19.10 shows the sequence of events
that occur when using converters to process localized information input.

[      ]{style=""}Consider Figure 19.8. In this form, all the details
are entered in French including the monthly salary field. As a result,
when the form is submitted, before the form values are populated, there
has to be an intermediate process which will get the user's preferred
locale, parse the string version of the monthly salary accordingly and
finally create an object of type Double and populate it into the form.

[      ]{style=""}Enter the Converter. The Converter is an abstract
class in the javax.faces.convert package and has two methods that are
implemented by the subclasses. These methods are:

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}getAsObject(FacesContext
fc, UIComponent component, String inputValue) throws ConverterException

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}getAsString(FacesContext
fc, UIComponent component, Object formValue) throws ConverterException

[      ]{style=""}The getAsObject method receives a String as input and
formats it according to the user's specifications and returns an object.

[      ]{style=""}Similarly, the getAsString method receives an Object
as input, and returns a localized String representation.

In order to use JSF Converters, you have to do the following:

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}Implement
the Converter interface

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}Register
the converter with your application

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}Use
the Converter in your JSP page

 

Implement the Converter interface

You can create a custom converter like the one shown in Listing 19.21.

Listing 19.21 MyConverter.java

 

public class MyConverter implements Converter {

[   ]{style=""}public Object getAsObject(FacesContext context,

[                             ]{style=""}UIComponent component,

[                       ]{style=""}[ ]{style=""}[      ]{style=""}String
newValue)

[   ]{style=""}throws ConverterException {

[   ]{style=""}...

[   ]{style=""}}

 

 

[   ]{style=""}public Object getAsString(FacesContext context,

[                             ]{style=""}UIComponent component,

[                       ]{style=""}[ ]{style=""}[      ]{style=""}Object
newObject)

[   ]{style=""}throws ConverterException {

[   ]{style=""}...

[   ]{style=""}}

}

 

Register the converter with your application

In the Faces configuration file /WEB-INF/faces-config.xml, you will have
to add an entry for your Converter as follows:

[  ]{style=""}\<converter\>

[    ]{style=""}\<description\>My cool converter\</description\>

[    ]{style=""}\<converter-id\>MyConverter\</converter-id\>

[    ]{style=""}\<converter-class\> foo.bar.MyConverter
\</converter-class\>

[  ]{style=""}\</converter\>

[ ]{.underline}

Use the Converter in your JSP page

Finally, in your JSP page, you can add this converter to a JSF component
as:

\<h:input_text id=\"myField\" valueRef=\"FooBarForm.myField\"
converter=\"MyConverter\"/\>

[ ]{.underline}

And you are done! Now let us come back to our localization example.
Consider figure 19.15. It shows the sequence of events that occur when a
JSF form containing localized data is submitted. The following steps are
executed:

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}User
submits the form

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}In
the Apply Request Values phase, the values from the request are to be
populated in the model bean's properties. At this point, the JSF
implementation invokes the getAsObject method on any registered
converters in the form fields.

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}The
getAsObject method in the Converter parses the input String and creates
a java Object that is populated into the form bean.

[·[       
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}]{style="font-family: Symbol;"}During
the Render Response phase a JSP page will be rendered. During this
phase, the JSF implementation calls the getAsString method on the
Converter which takes the fields for which a converter has been
specified and passes to the converter the Object value of each field.
This object value is then parsed according to locale and the string
version sent to the output for display.

[![](Ch19-I18N_and_L10N_files/image029.jpg){v:shapes="_x0000_s1192"
height="455"
width="623"}]{style="position: absolute; z-index: 14; left: 0px; margin-left: 5px; margin-top: 3px; width: 623px; height: 455px;"}[     
]{style=""}

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

Figure 19.15 The sequence of events that take place when using
converters to process localized input

In our case, our converter implementation, let's call it
LocaleSpecificCurrencyConverter is shown in Listing 19.22.

 

Listing 19.22 LocaleSpecificCurrencyConverter.java

public class LocaleSpecificCurrencyConverter implements Converter {

 

/\*\*

[ ]{style=""}\* Receives the string value of an input number, formats it
according to a locale and returns an object

[ ]{style=""}\*/

[ ]{style=""}public Object getAsObject(FacesContext context, UIComponent
component,

[      ]{style=""}String newValue) throws ConverterException {

[      ]{style=""}\...

[ ]{style=""}}

[ ]{style=""}

/\*\*

[ ]{style=""}\* Receives the object value from a form, formats it
according to a locale

[ ]{style=""}\* and returns a String version for output

[ ]{style=""}\*/

[ ]{style=""}public Object getAsString(FacesContext context, UIComponent
component,

[      ]{style=""}Object newValue) throws ConverterException {

[      ]{style=""}\...

[ ]{style=""}}

[ ]{style=""}

} [    ]{style=""}

 

Now, it is time to take a look at Figure 19.10. Here, the user submits
the JSF form containing the localized information for monthlySalary. In
the Apply Request Values phase, the JSF implementation invokes the
getAsObject method on the LocaleSpecificCurrencyConverter instance. This
method is shown in Listing 19.23

 

Listing 19.23 The getAsObject method in LocaleSpecificCurrencyConverter

public Object getAsObject(FacesContext context,

[            ]{style=""}[              ]{style=""}UIComponent component,

[                          ]{style=""}String newValue)

throws ConverterException {

 

[   ]{style=""}HttpSession session[  ]{style=""}= (HttpSession)
context.getExternalContext().getSession(true);

[   ]{style=""}Locale usersLocale = (Locale)
session.getAttribute(\"userLocale\");\|#1

[   ]{style=""}if(usersLocale == null) {

[      ]{style=""}usersLocale = Locale.getDefault();

[   ]{style=""}}

[   ]{style=""}context.setLocale(usersLocale); \|#2

[   ]{style=""}Double convertedValue = null;

[   ]{style=""}if ( newValue == null ) {

[      ]{style=""}return newValue;

[   ]{style=""}}

[   ]{style=""}newValue = newValue.trim();

[   ]{style=""}NumberFormat numberFormat =

[   
]{style=""}[            ]{style=""}NumberFormat.getNumberInstance(usersLocale);
\|#3

[   ]{style=""}Number numericValue = null;

[   ]{style=""}try {

[      ]{style=""}numericValue = numberFormat.parse(newValue); \|#4

[   ]{style=""}}

[   ]{style=""}catch(ParseException pe) {

[      ]{style=""}throw new ConverterException(Util.getExceptionMessage(

[                        ]{style=""}Util.CONVERSION_ERROR_MESSAGE_ID));
\|#5

[   ]{style=""}}

[   ]{style=""}convertedValue = new Double(numericValue.doubleValue());[
]{style=""}\|#6

[   ]{style=""}return convertedValue;

}

 

(annotation)\< #1 Get the preferred locale from the session\>

(annotation)\< #2[  ]{style=""}Set the locale in the Faces context\>

(annotation)\< #3 Create a NumberFormat instance for the locale\>

(annotation)\< #4 Parse the input string using the NumberFormat
instance\>

(annotation)\< #5 Throw a ConverterException if unable to parse input
data\>

(annotation)\< #6 Create a Double instance from the Number obtained in
step 4 and return it\>

 

In the getAsObject method, a String value of the monthlySalary is
obtained. The user's preferred locale is obtained from the session as:

[   ]{style=""}Locale usersLocale = (Locale)
session.getAttribute(\"userLocale\");

 

Next, a NumberFormat instance is created for the preferred locale as:

[   ]{style=""}NumberFormat numberFormat=
NumberFormat.getNumberInstance(usersLocale);

 

The String value is parsed using the NumberFormat instance, to obtain a
Number object. Any exceptions at this time are returned as a
ConverterException. From the Number instance, a Double value is created
and returned as shown:

[   ]{style=""}convertedValue = new Double(numericValue.doubleValue());[
]{style=""}

[   ]{style=""}return convertedValue;

 

 

Listing 19.24 The getAsString method in LocaleSpecificCurrencyConverter

 

public String getAsString(FacesContext context, UIComponent component,

[   ]{style=""}Object value) throws ConverterException {

[   ]{style=""}HttpSession session[  ]{style=""}= (HttpSession)
context.getExternalContext().getSession(true);

[   ]{style=""}Locale usersLocale = (Locale)
session.getAttribute(\"userLocale\");\|#1

[   ]{style=""}if(usersLocale == null) {

[      ]{style=""}usersLocale = Locale.getDefault();

[   ]{style=""}}

[   ]{style=""}context.setLocale(usersLocale); \|#2

 

[   ]{style=""}String inputVal = null;

[   ]{style=""}if ( value == null) {

[      ]{style=""}return null;

[   ]{style=""}}

[   ]{style=""}// value must be of the type that can be cast to a
String.

[   ]{style=""}try {

[      ]{style=""}inputVal =
value.toString();[                           ]{style=""}

[      ]{style=""}if(inputVal.equals(\"\")) {

[            ]{style=""}return null;

[      ]{style=""}}

[   ]{style=""}} catch (ClassCastException ce) {

[      ]{style=""}throw new ConverterException(Util.getExceptionMessage(

[                        ]{style=""}Util.CONVERSION_ERROR_MESSAGE_ID));

[   ]{style=""}}

[   ]{style=""}NumberFormat numberFormat =

[                ]{style=""}NumberFormat.getNumberInstance(usersLocale);
\|#3

[   ]{style=""}Number num = null;

[   ]{style=""}try {

[      ]{style=""}num =
numberFormat.parse(inputVal);[                    ]{style=""}\|#4

[   ]{style=""}}

[   ]{style=""}catch(ParseException pe) {

[      ]{style=""}throw new ConverterException(Util.getExceptionMessage(

[                       
]{style=""}Util.CONVERSION_ERROR_MESSAGE_ID));[  ]{style=""}\|#5

[   ]{style=""}}

[   ]{style=""}if(num == null) {

[      ]{style=""}return null;

[   ]{style=""}}

[   ]{style=""}else {

[      ]{style=""}Double doubleValue = new Double(num.doubleValue());

[      ]{style=""}return
doubleValue.toString();[                         ]{style=""}\|#6

[   ]{style=""}}

}

(annotation)\< #1 Get the preferred locale from the session\>

(annotation)\< #2[  ]{style=""}Set the locale in the Faces context\>

(annotation)\< #3 Create a NumberFormat instance for the locale\>

(annotation)\< #4 Parse the input string using the NumberFormat
instance\>

(annotation)\< #5 Throw a ConverterException if unable to parse input
data\>

(annotation)\< #6 Create a String instance of the input object and
return it\>

 

The getAsString method is similar to the getAsObject method except that
this method takes an input String, extracts the locale from the session
as before, creates a NumberFormat instance and returns a Double value
obtained from parsing the String value.

 

19.3.6 The J2EE Internationalization service

So far you have seen the various tried and tested ways to
internationalize a web application. In this section we briefly cover a
new service that aims at internationalizing the various aspects of a
J2EE application. The Java Community Process (JCP) is considering a new
Java Specification Request called "Internationalization Service for
J2EE" (JSR 150)

[      ]{style=""}According to the specification, "The
Internationalization Service enables distributed localization within
Enterprise Java applications by transparently propagating and managing
localization information within relevant J2EE application components."

[      ]{style=""}This service aims at localizing applications
distributed across multiple JVMs. It requires support from J2EE
architectural elements and middleware including the application server,
the EJB and the Web containers, rudimentary support from the Application
Client Container.[  ]{style=""}Hopefully, this service when implemented
will standardize the Internationalization process for a J2EE
application.

[      ]{style=""}The past few sections showed you the various ways of
internationalizing your web applications. The next section gives some
helpful ideas regarding some points to consider before going global.

8.4[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Internationalization
recommended practices

In the previous sections you saw how to internationalize and localize
J2EE web applications. There were different approaches discussed. As
always, there are several solutions to a given problem and some of these
approaches might be better suited than others.

[      ]{style=""}This section lists some practices that are recommended
while localizing a web application. Here are a few:

1.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Give
the user a choice of locale at the beginning of an application.[ 
]{style=""}Show only those locales which your application supports.

2.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}One
of the first things to do before actually getting into the
implementation details is to identify culturally sensitive data. This
has been explained in detail in section, 19.1.3, "What can be
internationalized".

3.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}In
the implementation, it is always better to customize your application
such that a single JSP can display localized text messages instead of a
"One JSP page per locale" approach.

4.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}After
the localizable text has been identified create resource bundles (one
per locale) to hold this information.

5.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}If
your application deals with comparing or sorting strings in native
languages, use the Collator class to perform these operations.

6.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}In
JSP 1.1 the \<jsp:include\> tag is preferred to the[ 
]{style=""}\<%@include%\> directive as the [contentType:charset of the
included page cannot be set independently of the including page. The
\<jsp:include\> tag offers more control over the page encoding. A simple
rule of thumb to follow is: If your JSP pages are generating a lot of
dynamic content, then the \<jsp:include\> tag is your best option.
]{style="color: windowtext;"}

7.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}If
you are dealing with files that are encoded in any language that is not
Latin-1 or Unicode compliant, use the native2ascii tool to convert it to
a Unicode format as explained in section 19.1.4.

8.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}If
your application has to display images based on locale, keep the images
in a folder representing that locale. At runtime, the images need to be
looked up from the respective folder based on locale.

9.[     
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Instances
of java.text.Format and its subclasses are not synchronized. It is a
good idea to create separate instances of these classes for each thread.
If there are multiple threads accessing a single format instance, then
external synchronization needs to be applied to the formatter.

10.[  
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Use
Unicode character encoding whenever possible.

11.[  
]{style="font-family: \"Times New Roman\"; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal; -x-system-font: none;"}Sometimes
there might be a requirement that the "alt" attribute in an image tag
should have an internationalized message when an image is not displayed.
In such cases, you can either explicitly get the localized message from
the resource bundle using a scriptlet or use it or for a cleaner
solution, you can write a custom tag to extract and display these
localized messages.

[      ]{style=""}\<img src= "myimage.gif" alt="localized message"\>

[            ]{style=""}can be replaced with something like:

[      ]{style=""}\<mytaglib:myimagetag src="myimage.gif"
alt="key.to.localized.message"\>

 

19.5 Summary

In this chapter we started with what Internationalization and
localization are, their need and thei advantages. We also got a quick
overview of the Java and Struts Internationalization API.[ 
]{style=""}Then we went on to see the various ways to internationalize
the web tier using Struts, Tiles, JSF and JSTL tags. We also saw how to
process localized input using Struts applications and JSF. Finally, we
came across some helpful ideas while internationalizing the web tier.

 
:::
