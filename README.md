# Regular-Expressions-Date-and-Time

► Regular expression

Regular expression is a sequence of pattern that defines a string. It is used to denote regular languages.

It is also used to match character combinations in strings. String searching algorithm used this pattern to find the operations on string.

In regular expression, x* means zero or more occurrence of x. It can generate {e, x, xx, xxx, xxxx,.....}

In regular expression, x+ means one or more occurrence of x. It can generate {x, xx, xxx, xxxx,.....}

Operations on Regular Language

The various operations on regular language are:

• Union: If L and M are two regular languages then their union L U M is also a union.

L U M = {s | s is in L or s is in M}  

Intersection: If L and M are two regular languages then their intersection is also an intersection.

L ⋂ M = {st | s is in L and t is in M}  

Kleene closure: If L is a regular language then its kleene closure L1* will also be a regular language.


L* = Zero or more occurrence of language L.  

Example

Write the regular expression for the language:


L = {abn w:n ≥ 3, w ∈ (a,b)+}


Solution:

The string of language L starts with "a" followed by atleast three b's. Itcontains atleast one "a" or one "b" that is string are like abbba, abbbbbba, abbbbbbbb, abbbb.....a

So regular expression is:


r= ab3b* (a+b)+

Here + is a positive closure i.e. (a+b)+ = (a+b)* - ∈


• A regular expression is a kind of pattern that can be applied to text (Strings, in Java).

• A regular expression either matches the text (or part of the text), or it fails to match.

If a regular expression matches a part of the text, then you can easily find out which part.

If a regular expression is complex, then you can easily find out which parts of the regular expression match which parts of the text
With this information, you can readily extract parts of the text, or do substitutions in the text.

• Regular expressions are an extremely useful tool for manipulating text.

• Regular expressions are heavily used in the automatic generation of Web pages.

► Perl and Java

• The Perl programming language is heavily used in server-side programming, because

• Much server-side programming is text manipulation.

• Regular expressions are built into the syntax of Perl.

• Beginning with Java 1.4, Java has a regular expression package, java.util.regex

Java’s regular expressions are almost identical to those of Perl.

This new capability greatly enhances Java 1.4’s text handling.

Regular expressions in Java 1.4 are just a normal package, with no new syntax to support them
Java’s regular expressions are just as powerful as Perl’s, but
Regular expressions are easier and more convenient in Perl.

First, you must compile the pattern.

import java.util.regex.*;

Pattern p = Pattern.compile("[a-z]+");

Next, you must create a matcher for a specific piece of text by sending a message to your pattern
Matcher m = p.matcher("Now is the time");

Points to notice:
Pattern and Matcher are both in java.util.regex
Neither Pattern nor Matcher has a public constructor; you create these by using methods in the Pattern class
The matcher contains information about both the pattern to use and the text to which it will be applied.

• abc		
exactly this sequence of three letters


• [abc]		

any one of the letters a, b, or c


• [^abc]		

any character except one of the letters a, b, or c
			(immediately within an open bracket, ^ means “not,”
		 but anywhere else it just means the character ^)


• [a-z]		

any one character from a through z, inclusive


• [a-zA-Z0-9]	

any one letter or digit


Some predefined character classes

any one character except a line terminator


\d		a digit: [0-9]


\D		a non-digit: [^0-9]


\s		a whitespace character: [  \t\n\x0B\f\r]


\S		a non-whitespace character: [^\s]


\w		a word character: [a-zA-Z_0-9]


\W	a non-word character: [^\w]


Boundary matchers

These patterns match the empty string if at the specified position:

^	the beginning of a line


$	the end of a line


\b	a word boundary


\B	not a word boundary


\A	the beginning of the input (can be multiple lines)


\Z	the end of the input except for the final terminator, if any


\z	the end of the input


\G	the end of the previous match


import java.util.regex.*;

    
public class RegexTest {

    public static void main(String args[]) {
    
        String pattern = "[a-z]+";
        
        
        String text = "Now is the time";
        
        
        Pattern p = Pattern.compile(pattern);
        
        
        Matcher m = p.matcher(text);
        
        
        while (m.find()) {
        
        
            System.out.print(text.substring(m.start(), m.end()) + "*");
       
       
       }

}
 
 
}

       
Output: 

ow*is*the*time*


Regular expressions are not easy to use at first

It’s a bunch of punctuation, not words

The individual pieces are not hard, but it takes practice to learn to put them together correctly

Regular expressions form a miniature programming language

It’s a different kind of programming language than Java, and requires you to learn new thought patterns

In Java you can’t just use a regular expression; you have to first create Patterns and Matchers

Java’s syntax for String constants doesn’t help, either
Despite all this, regular expressions bring so much power and convenience to String manipulation that they are well worth the effort of learning.


► Java Date and Time

• Why do we need new Java Date Time API?

Before we start looking at the Java 8 Date Time API, let’s see why do we need a new API for this. There have been several problems with the existing date and time related classes in java, some of them are:


• The java.time, java.util, java.sql and java.text packages contains classes for representing date and time. Following classes are important for dealing with date in Java.

► Java 8 Date/Time API

Java has introduced a new Date and Time API since Java 8. The java.time package contains Java 8 Date and Time classes.

--> java.time.LocalDate class

--> java.time.LocalTime class

--> java.time.LocalDateTime class

--> java.time.MonthDay class

--> java.time.OffsetTime class

--> java.time.OffsetDateTime class

--> java.time.Clock class

--> java.time.ZonedDateTime class

--> java.time.ZoneId class

--> java.time.ZoneOffset class

--> java.time.Year class

--> java.time.YearMonth class

--> java.time.Period class

--> java.time.Duration class

--> java.time.Instant class

--> java.time.DayOfWeek enum

--> java.time.Month enum

--> Classical Date/Time API


But classical or old Java Date API is also useful. Let's see the list of classical Date and Time classes.

--> java.util.Date class

--> java.sql.Date class

--> java.util.Calendar class

--> java.util.GregorianCalendar class

--> java.util.TimeZone class

--> java.sql.Time class

--> java.sql.Timestamp class

--> Formatting Date and Time


We can format date and time in Java by using the following classes:


--> java.text.DateFormat class

--> java.text.SimpleDateFormat class

--> Java Date and Time APIs

--> Java provide the date and time functionality with the help of two packages java.time and java.util. The package java.time is introduced in Java 8, and the newly introduced classes tries to overcome the shortcomings of the legacy java.util.Date and java.util.Calendar classes.


• Classical Date Time API Classes

The primary classes before Java 8 release were:

--> Java.lang.System: The class provides the currentTimeMillis() method that returns the current time in milliseconds. It shows the current date and time in milliseconds from January 1st 1970.

--> java.util.Date: It is used to show specific instant of time, with unit of millisecond.

--> java.util.Calendar: It is an abstract class that provides methods for converting between instances and manipulating the calendar fields in different ways.

--> java.text.SimpleDateFormat: It is a class that is used to format and parse the dates in a predefined manner or user defined pattern.

--> java.util.TimeZone: It represents a time zone offset, and also figures out daylight savings.

► Drawbacks of existing Date/Time API's
Thread safety: The existing classes such as Date and Calendar does not provide thread safety. Hence it leads to hard-to-debug concurrency issues that are needed to be taken care by developers. The new Date and Time APIs of Java 8 provide thread safety and are immutable, hence avoiding the concurrency issue from developers.

• Bad API designing: The classic Date and Calendar APIs does not provide methods to perform basic day-to-day functionalities. The Date and Time classes introduced in Java 8 are ISO-centric and provides number of different methods for performing operations regarding date, time, duration and periods.
Difficult time zone handling: To handle the time-zone using classic Date and Calendar classes is difficult because the developers were supposed to write the logic for it. With the new APIs, the time-zone handling can be easily done with Local and ZonedDate/Time APIs.
New Date Time API in Java 8
The new date API helps to overcome the drawbacks mentioned above with the legacy classes. It includes the following classes:


--> java.time.LocalDate: It represents a year-month-day in the ISO calendar and is useful for representing a date without a time. It can be used to represent a date only information such as a birth date or wedding date.

--> java.time.LocalTime: It deals in time only. It is useful for representing human-based time of day, such as movie times, or the opening and closing times of the local library.

--> java.time.LocalDateTime: It handles both date and time, without a time zone. It is a combination of LocalDate with LocalTime.

--> java.time.ZonedDateTime: It combines the LocalDateTime class with the zone information given in ZoneId class. It represent a complete date time stamp along with timezone information.

--> java.time.OffsetTime: It handles time with a corresponding time zone offset from Greenwich/UTC, without a time zone ID.


--> java.time.OffsetDateTime: It handles a date and time with a corresponding time zone offset from Greenwich/UTC, without a time zone ID.

--> java.time.Clock : It provides access to the current instant, date and time in any given time-zone. Although the use of the Clock class is optional, this feature allows us to test your code for other time zones, or by using a fixed clock, where time does not change.

--> java.time.Instant : It represents the start of a nanosecond on the timeline (since EPOCH) and useful for generating a timestamp to represent machine time. An instant that occurs before the epoch has a negative value, and an instant that occurs after the epoch has a positive value.


--> java.time.Duration : Difference between two instants and measured in seconds or nanoseconds and does not use date-based constructs such as years, months, and days, though the class provides methods that convert to days, hours, and minutes.

--> java.time.Period : It is used to define the difference between dates in date-based values (years, months, days).

--> java.time.ZoneId : It states a time zone identifier and provides rules for converting between an Instant and a LocalDateTime.

--> java.time.ZoneOffset : It describe a time zone offset from Greenwich/UTC time.

--> java.time.format.DateTimeFormatter : It comes up with various predefined formatter, or we can define our own. It has parse() or format() method for parsing and formatting the date time values.

► LocalDate


package com.journaldev.java8.time;

 
import java.time.LocalDate;
import java.time.Month;
import java.time.ZoneId; 
public class LocalDateExample {
 
    public static void main(String[] args) {
         
        //Current Date
        LocalDate today = LocalDate.now();
        System.out.println("Current Date="+today);
         
        //Creating LocalDate by providing input arguments
        LocalDate firstDay_2014 = LocalDate.of(2014, Month.JANUARY, 1);
        System.out.println("Specific Date="+firstDay_2014);
         
    
        LocalDate todayKolkata = LocalDate.now(ZoneId.of("Asia/Kolkata"));
        System.out.println("Current Date in IST="+todayKolkata
      
        LocalDate dateFromBase = LocalDate.ofEpochDay(365);
        System.out.println("365th day from base date= "+dateFromBase);
         
        LocalDate hundredDay2014 = LocalDate.ofYearDay(2014, 100);
        System.out.println("100th day of 2014="+hundredDay2014);
    }
 
}


► LocalDateTime


package com.journaldev.java8.time;

 
import java.time.LocalDate;
import java.time.LocalDateTime;
import java.time.LocalTime;
import java.time.Month;
import java.time.ZoneId;
import java.time.ZoneOffset;
 
public class LocalDateTimeExample {
 
    public static void main(String[] args) {
         
        //Current Date
        LocalDateTime today = LocalDateTime.now();
        System.out.println("Current DateTime="+today);
         
        //Current Date using LocalDate and LocalTime
        today = LocalDateTime.of(LocalDate.now(), LocalTime.now());
        System.out.println("Current DateTime="+today);
         
        
        LocalDateTime specificDate = LocalDateTime.of(2014, Month.JANUARY, 1, 10, 10, 30);
        System.out.println("Specific Date="+specificDate);
        
        LocalDateTime todayKolkata = LocalDateTime.now(ZoneId.of("Asia/Kolkata"));
        System.out.println("Current Date in IST="+todayKolkata);

        LocalDateTime dateFromBase = LocalDateTime.ofEpochSecond(10000, 0, ZoneOffset.UTC);
        System.out.println("10000th second time from 01/01/1970= "+dateFromBase);
 
    }
 
}
