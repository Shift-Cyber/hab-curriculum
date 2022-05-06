# [Miscellaneous] Password Security Introduction
*Your password's probably bad, let's make it better.*

![password security](.rsrc/banner.png)

# Introduction
There's usually only one thing between you and the bad guys... one way to access all your important stuff online--passwords! In this lesson you're going to figure out how your current password stands up to an attacker and how you can make it better. After all, only you should be able to post stuff on your Instagram, right? You'll explore how passwords are stored and importantly, how attackers can try to steal them to access your important accounts. After that, we'll look at a few catastrophes that have changed how things are done, specifically to see what can happen if these important rules aren't followed. Finally, we'll take a look at some tools you can use to be as secure as possible online, as well as some of the things big companies do to keep *your* data as safe as possible!

# Objectives
1. [How strong is YOUR password?](#How-Strong-is-YOUR-Password)
2. [Storing and attacking passwords](#Storing-and-Attacking-Passwords)
3. [Designing strong, memorable passwords](#Designing-Strong-Memorable-Passwords)
4. [The gold standard (password managers)](#The-Gold-Standard-Password-Managers)
5. [Other authentication: SSO & Federated Identity](#Other-Authentication-SSO--Federated-Identity)

# Lesson
## How Strong is YOUR Password?
Let's get a baseline. It is fairly straightfoward to calculate how secure your password is and we'll explore this later. For now, we can use an online tool to see how our current password holds up against an attacker. Visit this website and see how long it would take a bad guy with an average laptop to crack YOUR password!

https://www.security.org/how-secure-is-my-password/

Now that you've done that, why did you do that! I'm just some guy on the internet, now I have your password!! Just kidding, I wouldn't do that to you... in all seriousness you can see that this tool is actually opensource and maintained on a public site that hosts code like this, called GitHub. If the tool says it would take less than a year to crack your password, while this may be true for average laptops, specalized tools that the bad guys have can crack your password in minutes!! Hopefully your password stood up alright, but if not its time to learn how to make it better so we can keep people out of our stuff!

Here's the source code for the above tool if you want the proof that I don't have your password: 
https://github.com/howsecureismypassword

## Storing and Attacking Passwords
It would be awesome if we could just write down our password on a piece of paper and put it in a high-security vault like this [one](https://vaultdoorsafebox.en.made-in-china.com/product/jCOnxkmEhqWl/China-Door-Supplier-Stainless-Security-Vault-Panel-Round-Vault-Door.html). But in this cause, if an attacker breaks into the vault, they still get our password. Fortunately, there is a better way! We can put our password through something called a hashing algorithm. A hash is a "one way" algorithm that takes our input and generates a specific output, ensuring that we can't figure out what the input was if we only have the "hash." You can think of this like the ingredients for baking a cake. If you just have the cake, you cant figure out exactly what was used to bake it--if you could there probably wouldn't be many bakerys out there. But at the same time, the same ingredients with the same procedure will always produce the same output. If you have the secret recipie (input/password), you can produce the correct cake (hash/login).

<br><img src=".rsrc/cake.jpg" alt="clock" width="300" style="display:block; margin:auto;"/><br>

When the computer wants to check our login attempt it takes our provided input and hashes it. If the hash of the provided input matches the hash stored in the vault, then we know the same input was provided. Now if the attacker gets into the vault, they can't recover the original password and they have to guess every possible combination to figure out what the original value that resulted in that hash was, giving us time to change it before they figure it out.

Lets use a simple example like a 4 digit pin code. In this case our "password" could be something like 1264, 7311, 1236 etc. **The maximum possible combinations is the number of possible characters in a position**, so in this case the numbers 0-9, **raised to the power of the number of possible characters in the password**, so 4. This makes the calculation: ```(charTypes)^charCount``` == ```10^4``` == ```10,000```. There are usually 95 printable characters on a standard english keyboard, which means an 8 digit password has a possible number of ```6.63e15``` different combinations. This calculation would be done as ```95^8```. Noticed that while the constant number ```95``` is bigger than the exponent ```8```, if we increase both numbers by ```1```, we get many more cobinations by increasing our length (```8```). This is because the length is an exponential value rather than a multiplicative one.



## Designing Strong, Memorable Passwords
Lets hear from Bobby Richter of Consumer Reports. In this video the two gentlemen discuss some tricks to building and remembering strong passwords. The two also talk about password managers.

[![How to Create Strong Passwords](https://img.youtube.com/vi/ZL6446ShQ08/0.jpg)](https://www.youtube.com/watch?v=ZL6446ShQ08)

One point to make about this video, while it is very good, is that it's very important to ensure that your words are not straight out of a dictionary. Attackers can guess combinations of words in a dictionary very rapidly with tools, so while the password ```thebigbrowndog``` isn't that strong, a mangled version like ```thEbigBr0wndog``` is actually very solid.

Key Takeaways:
- Don't use personal information, be random
- Incorporate special characters and numbers
- Length is more important than anything else


## The Gold Standard (Password Managers)
At the end of the day, if we could remember a 30 character completely randomized password string of characters, that would likely be the least "guessable" password. While most human beings can't do this efficiently, there is a solution that allows us to use a completely random password for every site. The solution is a password manager. Password managers are like a vault where we can put all our sensitive information. Passwords, notes, payment information, etc. The idea is that for most people, if you can compromise an email account you can reset passwords on most accounts and get access to data. Instead of having an email accoutn as the single point of failure, we can use a tool that provides a number of added benefits.

Password management providers inherently focus on security, as while they are a high-value target just like email, the implication is much more immediate. Most of these tools are setup as web browser extensions that will automatically fill passwords in for you. In short, you use a strong memorably password for the password manager, as we discussed above and then the password manager allows you to use long, extremely complex and unique passwords on every individual website.


## Other Authentication: SSO & Federated Identity
The last part of this section is a discussion about moving away from passwords entierly. What if we could login one place and automatically get access to everything? This way there is no need for a password manager at all. Well this is possible and its being done with a technology aptly called Single Sign On (SSO).

If you've ever logged in somewhere using your Google account, you've used single sign on. Federated identity is another closely related technology and both are used to allow people to prove they are who they are in a single place, before accessing things they are supposed to have access to in various places across the internet.


# The Real World, Prolific Breaches
Let's now take a look at why these concepts matter. We will see how RockYou demonstrated the importance of hashing, how some interesting tools came out of the prolific Adobe breach and how these concepts are still troubling even today, with Okta.

## 2009 - RockYou
In later lessons on password security where we cover storage in more depth as well as cracking passwords, you will start by using something called a wordlist. The first one you will start with, that is used by experts across the industry and is actually included in offensive Linux distributions, is called ```rockyou.txt```. Back in 2009 a company that was building apps for MySpace and Facebook was storing passwords without hashing. Attackers broke into the company and stole a list of every user account and their password. The wordlist mentioned previously is comprised of that data, sorted by the number of times each password was used. There are 14 million entires and the top password ```12345``` was used by 290,729 accounts on RockYou. This breach put RockYou out of business, largely due to the public affairs problems. This is one of the reasons hashing is absolutely critical; if passwords were hashed, it would have been much harder to create this list.

- https://en.wikipedia.org/wiki/RockYou
- https://techcrunch.com/2009/12/14/rockyou-hack-security-myspace-facebook-passwords/

## 2013 - Adobe Breach
What if there was a website where you could figure out if you're credentials have shown up in any breaches? Well it turns out there is and it's a result of 38 million Adobe accounts being compromised back in 2013. Troy Hunt "often did post-breach analysis of user credentials and kept finding the same accounts exposed over and over again." He had the idea to create a website where people could disclose compromised data they found on the darker parts of the internet and you could then put your email in to see if it had shown up in any of those breaches. Many of the HaB team members actually have had their accounts show up on this site. You can even sign up for email notifications. If you get a notification, so long as you have a sufficiently complex password and the organization was hashing passwords, you simply need to change your credentials and you will likely be okay. The haveibeenpwned website linked below has been an enormous contribution to the community over the years.

- https://www.bbc.com/news/technology-24740873
- https://haveibeenpwned.com/FAQs

## 2022 - Okta
Okta is a provider of SSO-type identity services for a variety of customers with critical resources on the internet. Just this year Lapsus$, a data extortion group, claimed access to these resources with admin authority. This allowed them to access a variety of Okta customers. High priority resources like authentication remain a key target for attackers, even today in 2022. From the article:

>Data extortion groups like Lapsus$ breach victims, but as opposed to encrypting confidential files like a ransomware operator would, these actors steal and hold on to victims' proprietary data, and publish it should their extortion demands not be met.

- https://techcrunch.com/2022/03/28/lapsus-passwords-okta-breach/
- https://www.bleepingcomputer.com/news/security/okta-investigating-claims-of-customer-data-breach-from-lapsus-group/

# Check YoSelf
## Q1 - Which of these passwords would take the longest to crack?
a. ```password123```<br>
b. ```securityI$C00l```<br>
c. ```TheBlackDogRanUpMyTree``` <---<br>
d. ```I'mLearningSecurity```<br>

## Q2 - Is using personal data like age or a pet's name a good way to create a memorable password?
a. ```yes```<br>
b. ```no``` <---<br>

## Q3 - How do we calculate the max number of guesses (complexity)?
a. ```(charTypes)^charCount``` <---<br>
b. ```charCount*timeToCrack```<br>
c. ```(charCount)^charTypes```<br>
d. ```timeToCrack*charCount```<br>

# Keep Going, Next Steps
Check out the following curated resources if you'd like to keep learning about this topic to dominate hard challenges.
1. John the Ripper - https://www.youtube.com/watch?v=XjVYl1Ts6XI
2. Hashing, Salting and Peppering - https://www.gearbrain.com/password-security-hashing-salting-peppering-2647766220.html
3. Understanding the Shadow File - https://www.cyberciti.biz/faq/understanding-etcshadow-file/
4. How SSO Works - https://www.onelogin.com/learn/how-single-sign-on-works
5. Password Cracking in Depth - https://www.youtube.com/watch?v=7U-RbOKanYs
