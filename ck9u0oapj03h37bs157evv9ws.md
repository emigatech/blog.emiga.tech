## Make PHP great again !

PHP (recursive acronym for PHP: Hypertext Preprocessor) is a widely-used open source general-purpose scripting language that is especially suited for web development and can be embedded into HTML.

Instead of lots of commands to output HTML (as seen in C or Perl), PHP pages contain HTML with embedded code that does “something” (in this case, output “Hi, I’m a PHP script!”). The PHP code is enclosed in special start and end processing instructions ```<?php``` and ```?>``` that allow you to jump into and out of "PHP mode."

What distinguishes PHP from something like client-side JavaScript is that the code is executed on the server, generating HTML which is then sent to the client. The client would receive the results of running that script, but would not know what the underlying code was. You can even configure your web server to process all your HTML files with PHP, and then there’s really no way that users can tell what you have up your sleeve.

The best things in using PHP are that it is extremely simple for a newcomer, but offers many advanced features for a professional programmer. Don’t be afraid reading the long list of PHP’s features. You can jump in, in a short time, and start writing simple scripts in a few hours.

Although PHP’s development is focused on server-side scripting, you can do much more with it. Read on, and see more in the What can PHP do? section, or go right to the introductory tutorial if you are only interested in web programming.

# Why is PHP considered as an outdated language for web development?

Brock McKean, Startup Engineer — “ PHP is not outdated. It’s just not relevant anymore for new websites if you are keeping up with all of the libraries and technologies available. Most website development is moving towards something like the MEAN stack.

Why? Because users want SPAs (Single Page Apps). This is a problem for the design of traditional server-client applications in the real of websites. Most websites have a static client page that is provided dynamic information from the server depending on the state of your session residing in the server. Where you actually are in the application and most of the data associated with your session is stored in the server. Page rendering, etc, is all handled in the server. This made a lot of sense before personal computers and wireless devices really started to have substantial processing power and memory enough to do this themselves. ”

Geoffrey Reemer, Happy PHP-coder — “ I believe PHP is catching up to modern views of how web languages should work quite fast. If you use a good framework such as Laravel or CakePHP, you can make very decent websites and applications. So PHP is definitely maturing and developing into a very sophisticated language.

I’m a happy PHP coder myself and I don’t consider it an outdated web development language. I wouldn’t mind giving Python a try, but the problem is that most webhosts favor PHP over other languages. Especially in my country the number of webhosts that support Python or Ruby is quite low compared to the hundreds of companies that work with PHP. I’m not prepared to pay extra just to be able to code in a “cool” language.”

Richard Watson, Web dev since 1999, mainly hacking on Ruby/Rails, Lua, Python and Golang — “ As computer languages go, PHP isn’t particularly old. However it was built in a very old-fashioned way at the start, you couldn’t really have said it was an example of functional programming or object orientation. Since then some extra parts have been bolted on, but conceptually it’s still not very modern either.

What it did well (at first) was integrate scripting with web pages in a way people could understand easily. In that regard it is now well and truly outdated. That doesn’t mean that it is not still widely used, but the modern ideas are now in the camp of other languages and the web frameworks that use them.”

# So...

PHP has had a love-hate relationship with much of the programming community for a while. An almost complete introduction to the topic of PHP hate can be found in the famous blog post PHP: a fractal of bad design. In this post, the author hilariously cuts down almost every aspect of the PHP language, and sets out a rather convincing argument for consigning PHP to the archives of programming history. The article is now slightly out of date (it was published in 2012), but much of its criticism remains valid.

Personally, I simultaneously love and hate pretty much every language that I have ever been introduced to. I love C and how it taught me low level programming concepts, but I hate how it takes two hours to try and join two strings together. I love Python because of the machine learning and Raspberry Pi communities, but I hate how it is practically impossible to achieve type safety and proper object oriented design. I love JavaScript and the asynchronous programming techniques that it has encouraged, but I hate how I need about 9000 dependencies in my ```node_modules``` directory to serve a hello world application on port 80.

There is lots that I love about PHP too. When I was younger, without funding for servers, shared free PHP hosting was all I had. It made object oriented programming accessible to me, and I love the package manager and its ecosystem.

With all that said, I passionaly hate the PHP core functions.

-  Want to map an array? ```array_map($callback, $input)```
-  Want to filter an array? ```array_filter($input, $callback)```
-  Want to get the type of a resource? ```get_resource_type($resource)```
-  Want to get the type of a variable? ```gettype($variable)```
-  Want to check if a variable is a string? ```is_string($variable)```
-  Want to check if a variable is set? ```isset($variable)```

PHP has all of the scars of a language that has been added to, without proper consideration, by many different people over a long period of time. The process for making changes to the language is now much stricter, but undoing the damage that was done is something that needs more discussion.

The alternative, is accepting these glaring inconsistencies as part of the language until it dies. The arguments for fixing or leaving these issues will not change over time, the only difference is that it might be easier to introduce backwards compatibility breaks in the future because more programmers will have gone elsewhere. Every year huge companies such as Google and Microsoft invest significant resources into trying to create a better programming language. If PHP wants to compete in the future with languages that have been designed with the benefit of hindsight, it has to clean out the crap every now and then.

In theory, the process for fixing the PHP core functions is simple. The first step is to introduce deprecations to functions that need to be replaced, and ensure that replacements are available and recommended for use. After a period of time, the deprecated functions that nobody is using any more can be removed.

Good replacements have been discussed before too. There was an RFC for fixing the inconsistent function names that was tabled in 2015 but never made it anywhere. My favourite suggestion, is that introducing scalar objects could open the door for a new API that is inspired by common sense rather than the C POSIX library.

```
// Rather than 
$lowerCaseFruit = ['apples', 'oranges', 'grapes'];  
$upperCaseFruit = array_map(function ($fruit) {     
    return strtoupper($fruit); 
}, $lowerCaseFruit);  
// We could have 
$lowerCaseFruit = ['apples', 'oranges', 'grapes'];  
$upperCaseFruit = $lowerCaseFruit->map(function ($fruit) {
   return $fruit->toUpper(); 
});
``` 

In reality, the process for fixing the PHP core functions is more difficult. The first step is actually convincing the PHP internals group that this cause is worth the effort and the backwards compatibility break. Joining the internals community is a pretty opaque process and it takes time (and goat sacrifices) to accrue the karma and respect necessary to actually action something yourself. But, if the wider community bangs its collective drum loudly enough, there is a chance that some of the key players in the group will set their brilliant minds to this task.

The reason for this post, is that the release of PHP 8 is current being discussed on the internals mailing list. The current suggestion is that PHP 7.3 (which is about to feature freeze) will be the last version before PHP 8 (except for a deprecations only PHP 7.4). A feature as major as this would almost certainly be rolled into a major version, and there are a lot of significant features already tabled for PHP 8 with no mention of cleaning up the core functions.

If we want to “Make PHP Great Again”, or at least “Make PHP Slightly Better Before 2025”, now is probably a good time to start banging that drum!

# September 2021
— PHP 8.0: The Upcoming Version of PHP and The Inclusion of JIT

As we know that PHP7 is awesome, it has huge improvements over PHP5, either we talk in terms of speed or performance. Also, it brought us the much-awaited scalar type hints for better user experience.

However, it would not be wrong to say that no language is perfect and requires to be updated now and then. So, when it comes to PHP 8, users’ expectations are very high. Well, the one place where everyone loves to see PHP8 go is into more real-time features. That’s because this feature will help not to use other languages in one PHP project only for the sake of real-time.

Due to the real-time era, the internet is transitioning to real-time. And, therefore, even users want their content fast. Few languages already have something for real-time purposes like JavaScript has Node.js, Python has Tornado, but PHP still doesn’t have anything. So, as per the announcement, we can suppose that PHP has evolved, and the next major legs are PHP 8.0.0 and the JIT (Just-in-Time) compilation.

# The Status of Just In Time (JIT) in PHP 8.0

There’s no information about the upcoming features of PHP 8.0 yet. Still, there is a strong conjecture of the inclusion of JIT in version 8.0 of PHP.

Though, to understand well about Just-in-Time (JIT) in PHP, let’s first learn about it in brief. A way of optimizing running code is Just in time compilation. This popular method is already used by the Java Virtual Machine (JVM), the popular V8 JavaScript VM from Google as well as HHVM. Hence, JIT is no silver bullet because both of these already use it.

Before the current evolution (PHP 7.x), the PHP development focused on improving PHP performance by using a JIT. Though, this attempt yielded substantial improvements in the benchmarks, yet proved to offer small improvements in real-world applications such as Joomla or WordPress.

Following the work which was done for version 7.0 of PHP and offering significant improvements in it, the performance in PHP 7.1 and PHP 7.2 have been rather modest. And, that’s because the team again started working on the JIT implementation. As of now, there is no deep analysis of the JIT PHP project, but there are some encouraging results.

# A Brief Introduction to JIT (Just-in-Time Compilation)

In computing, a way of executing computer code that involves compilation during the execution of a program — at run time — rather than before execution is what we called just-in-time (JIT) compilation (also called dynamic translation or run-time compilations).

Most frequently, this carries source code or more commonly bytecode translation to machine code, which is further executed directly. A JIT compiler implemented system continuously analyses the code being executed.

Also, it identifies parts of the code where the speedup gained from recompilation or compilation would outweigh the overhead of compiling that code.

# Why is JIT Introduced in PHP?

As we mentioned earlier, HHVM (an alternative runtime which Facebook developed & uses) utilizes JIT. It is even faster and better in comparison to the official PHP engine which was deployed in PHP 7.0.

So, because of the HHVM’s extreme popularity or high demand from the PHP community across the world to go for JIT Engine again, Zend and PHP Group is up for it and also determined to bring it up in the next major release PHP 8.0.
While a code written in PHP 5 is executed in PHP 7 even without change, as an outcome, the performance doubles. It is not because of the changes in the engine but the other optimizations in PHP 7.0.

Hence, we can believe that an update in the engine is certainly going to improve the performance in various folds. As we know the standard of HHVM, the performance level can easily double, or we can say that when words a code written for PHP 7 will implement in version 8.0, its time of execution will be halved.

In other words, to make the compilation during the execution of the program or runtime, JIT or Just-In-Time compilation is one of the best ways. And, as it’s best, there is no question of compilation before execution, especially where the huge time is consumed. It is possible to consider it to be a dynamic compilation process and yield a faster result that static or before runtime compilation surely.

Since many of the .Net framework implementations and the Java implementation are dependent on JIT already, it is okay for PHP to take advantage of dynamic compilation and enhance its performance up to the next level.

To understand more, let’s study the reasons in detail.

# 1. PHP Hits the Brick Wall
Since 7.0 version of PHP, many improvements have been made, including optimizations for HashTable, specializations in the compiler for certain sequences, specializations in the Zend VM for certain opcodes, and many more. And, it could be said that now PHP has reached the extent of its ability to be improved any further after so many improvements.

# 2. PHP for Non-Web Scenarios
After adding JIT in PHP, it will allow its use in scenarios for which it is not even considered today, i.e., in other non-web, CPU-intensive scenarios, especially where the performance benefits will be essential.

# 3. More Secure Implementations & Faster Innovations
The team will be able to develop built-in functions in PHP due to JIT support instead of C without any huge performance penalty. Yes, the use of JIT would make PHP less susceptible to overflows, memory management, and other similar issues associated with C-based development.

# How are the PHP Programs Compiled?

There is a virtual machine called Zend VM in PHP. The human-readable scripts are compiled into instructions, known as OpCodes, which are further understandable to the virtual machine.

Compiled instructions, OpCodes, are faster to translate to machine code as compared to the original PHP code, and the reason behind it is they are low-level. This execution stage is known at compile time. And, these compiled instructions aka opcodes are further executed by the Zend VM in the runtime stage.

To make compilation happen only when it is required, JIT is being implemented as an almost independent part of OPcache and an extension to cache the opcodes. Moreover, JIT will treat the instructions generated for the Zend VM as the intermediate representation in PHP. Further, to make the host of the code as the CPU directly and not the Zend VM, it will then generate architecture-dependent machine code.

# Release Date of PHP 8.0

According to previous updations, it takes years for the PHP team to come up with a major update. The last major version was released in December 2015. Though, we have a few minor updates every year like 7.0 to 7.1 and 7.2. Well, we can say the next major update is going to be PHP 8.0.

And, unlike the case where PHP 5.0 followed PHP 7.0 without the release of PHP 6, there will not be any omission this time.

The release of PHP 8.0 is not scheduled as it is a major leap and might take some years. But “Larry Garfield,” one of the reputed names in the PHP world, tweeted that PHP 8 is going to come out in September 2021.

# Concluding Thoughts

One of the major advantages that PHP has is it comes with every Linux system and also runs on Windows web servers. It complies that the language is likely to stay in the web-building ecosystem for quite some time. Recently, the language was also ranked eighth on the TIOBE Index, indicating a good deal of developer’s interest.

Based on the reports of Netcraft’s monthly web survey, the language’s presence is split mostly between Nginx web servers (29 percent), Microsoft (19 percent), and Apache (29 percent).










