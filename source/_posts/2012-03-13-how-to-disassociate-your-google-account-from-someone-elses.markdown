---
layout: post
title: "How to Disassociate Your Google Account From Someone Else's"
date: 2012-03-12 23:33
comments: true
categories: [Google, security]
---
I frequently get emailed new account information by people who are some subset
of [confused, foreign, children] and believe that my email address is their
email address. What I didn’t realize, or perhaps noticed but promptly forgot, is
that 10 solid people had used my GMail address as the backup address when they
created their Google account. This is the address to which you can send a
password reset should you ever lose access to your main account.

There is a rather large security flaw in this system, though granted one only
brought on by user error: None of these 10 accounts were verified by me as being
validly attached to their primary account. That is, when the confused user
listed my address as secondary, I either did not receive a confirmation email
before the two could be linked, or I certainly ignored it. The result is that
by virtue of a simple typo, a stranger can get full access to your GMail
account, and by extension probably everything you do online.

Not only that, but you can find out which accounts list yours as the secondary,
so even in the absence of verification notifications, a complete set of
exploitable accounts is readily available.

Happily for these 10 hapless internet users, I was not in a playful/evil mood
when I discovered this, so I spent the past 15 minutes severing the connections.
Which, by the way, is somewhat roundabout unless I missed a page.

1. Enter your email address at
   [https://www.google.com/accounts/ForgotPasswd?service=mail&fuOnly=1](https://www.google.com/accounts/ForgotPasswd?service=mail&fuOnly=1)
2. For each address sent to you, request a password reset from
   [GMail](https://www.gmail.com), or some other Google login
3. At the bottom of each password reset email is a link to disavow the account

I also sent these folks a nice email describing what had happened and
recommending that they be more careful in the future. I only hope they speak
English / read it properly, because otherwise I’m sure to get a good set of
interesting, upset replies.

