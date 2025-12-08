
  ░▒▓█▓▒░▒▓███████▓▒░ ░▒▓██████▓▒░         
  ░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓██▓▒░ 
  ░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░      ░▒▓██▓▒░ 
  ░▒▓█▓▒░▒▓███████▓▒░░▒▓█▓▒░               
  ░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░      ░▒▓██▓▒░ 
  ░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓██▓▒░ 
  ░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░░▒▓██████▓▒░         
                                                                                 
# IRC 

The godfather of all internet communications is IRC, or "Internet Relay Chat". In my opinion, all the other internet protocols are basically dressed up versions of irc. On irc you can create private or public "rooms" where you can send instant messages to other members of the "room". You can also have direct connections between clients for singular private conversations that are ephemeral.

In Irc lingo these "rooms" are called **channels**.

*Caution*: Irc has *a lot* of communities and some are "unseemly" if not illegal in some areas. Be cautious and know that venturing into the deep dark recesses of the internet can be dangerous and maybe scary. Stay in the channels you feel comfortable in and do not interact with strangers who make you feel unsafe. Irc allows you to block users from contacting you and also other safety features. 

## Irc Network / Server

We will use the public irc server called [Libera Chat](https://libera.chat/). One issue with Libera Chat that I noticed is that you immediately cannot connect form the TOR network. If you are using a regular Ubuntu/Linux installation this should not be an issue. 

If you are using [Tails](https://tails.net/) Linux OS, by default it uses the TOR network, which you will have to disable first in order to *initially* connect to Libera Chat and set up an account. For more info on using TOR to connect see the [TOR Guide Entry](https://libera.chat/guides/connect#accessing-liberachat-via-tor)

To connect to the server you need to use the server address and port number. The address you will need is `irc.libera.chat`. Irc typically runs on port number `6697`. In Japan you might get better performance using the East Asia specific server `irc.ea.libera.chat`. In Australia and New Zealand	you can try `irc.au.libera.chat`

For more information on Libera Chat, see these very helpful webpages:

* https://libera.chat/guides/
* https://libera.chat/guides/basics
* https://libera.chat/guides/faq

If you want you could just read those pages and skip to the the [Pidgin Installation](#the-pidgin-irc-client) section here but I will summarize some of the more salient points. :)

## Irc Clients

There are myriad irc clients in the open source world. For the purposes of this tutorial We will be discussing [Pidgin](https://pidgin.im/). 

* Pidgin Website: https://pidgin.im/

There are even several `terminal` based irc clients if you are so inclined. Here are some examples:

* [glirc](https://hackage.haskell.org/package/glirc#readme)
* [irssi](https://irssi.org/)

If you want more, see this list of pretty much every known ircV3 compliant client:

* [https://ircv3.net/software/clients](https://ircv3.net/software/clients)


### The Pidgin Messaging Client

Pidgin is a messaging client that can connect to many different messaging protocols. This document is focused on the irc protocol and thus we will set up Pidgin for irc usage.

#### Command Line Installation:

This is probably the easiest install despite it using the command line.

Open a terminal/console window and at the command line type to 2 following commands. You will be prompted to enter your password to authorize the installation.

```bash
sudo apt update
sudo apt install pidgin -y
```

After you enter your password and hit enter, you will see some terminal output and eventually it will stop. At this point Pidgin should be installed and you should see it in your programs menu. You can close the terminal or just ignore if for now.

#### Ubuntu Gui Installation:

In the Ubuntu Software installation client if you search for "Pidgin" you will likely find two options. They seem like they are slightly different. From what I can tell you want the **Pidgin "Instant Messaging Client"** rather than the *Pidgin Internet Messenger*. After you select the appropriate program and click install, you will be prompted for your password and the program will be installed. It should now be visible in your Ubuntu programs menu.

### Pidgin Set Up

When you start pidgin you will see the Add a network dialog window:

![Add Dialog](/images/pidgin_startup_add_dialog.png)

Click the **Add** button.

![Add Account Basic](/images/pidgin_add_account_basics_02.png)

In the basic tab: Set the Protocol to **irc**. Enter your preferred **username**, this how you will be seen by all other users. Then, set your preferred server.

- `irc.libera.chat` - Generally Server
- `irc.ea.libera.chat` - East Asia Server
- `irc.au.libera.chat` - Australia/New Zealand Server

 The **Local Ident** is what your own username name will look like to *yourself* in the channel window. Note: no Password is entered at this time. You may leave the Local Alias option blank as well. 

![Add Account Advanced](/images/pidgin_add_account_advanced.png)

In the advanced tab: Make sure Port is set to `6697`. For now do *not* check the "Use SSL" checkbox. Once we have set up a password on the irc server you will be able to use SSL so that your communications are encrypted. 

Click the "Save" button and the dialog will close. You will then see the empty and somewhat confusing "Pidgin Buddy List".

![Pidgin Buddy List](/images/pidgin_buddy_list_01.png)

Wait a few moments for Pidgin to connect to the irc server. At this point if you see a "Connection Error", so make sure you have followed all the steps as described above. 

At some point Pidgin will connect and show the "Available" status in the Buddy List.

![Pidgin Connection with Available Status](/images/pidgin_buddy_list_02.png)

Congratulations!! You are now connected to the irc server. You can now click the "Buddies" Menu item and Select "Join A Chat" from the menu.

![Join a Chat Dialog](/images/pidgin_join_a_chat_dialog.png)

In the Channel Box enter `#aiu_ubuntu_club`. Make sure include the `#` sign. All irc channel names start with a `#` sign. 

![#aiu_ubuntu_club channel](/images/pidgin_aiu_ubuntu_club_channel_window.png)

You have now joined your first irc channel. You will see your username in the right hand panel of the window. The topmost name is the name of the **channel admin**.

If you are the channel admin you might be in the wrong chat room. Check your channel name spelling. If you see my name, *hepaestus*, as an admin you are in the correct channel. I have entered some irc commands to make the club channel a more permanent non-ephemeral channel. 

On irc anyone can create a channel, you will be the owner of the channel **while you remain connected** and as long as no one else has started a channel with the same name. If you want to have a *more* permanent username and password, or a *more* permanent channel you need to use some magic irc commands. Which I will discuss [momentarily](#irc-commands).

You are now connected to the irc server and have entered a chat channel. You can now begin chatting with other users. Try saying "hello" and interacting with your fellow irc channel members.

You've come a long way, you **could** stop here and be done. If you do your entire presence on irc will be ephemeral. No usernames will be saved, you don't need a password to connect. You do not yet *own* your username and anyone can use *your* username after you disconnect. Any channels that you create will also be ephemeral and open to the irc public at large.

### Irc Commands

In order to setup your own username and account on the irc server you will have to enter a few commands directed to the server itself. You do this in the channel chat window itself by directing your chats to the server controller/user called **NickServ**.

#### Irc User Registration

For a complete description of this topic you can see the [Libera Chat Nickname Registration Guide](https://libera.chat/guides/registration). 

I will continue to summarize and hopefully simplify this here.

##### Registering Your Nickname

To create a less ephemeral irc presence you will first need to register your nickname.

In ANY chat window enter a command similar to this one below.

```irc
/msg NickServ REGISTER YourComplexStrongPassword youremail@example.com
```

##### Sidebar: Password Generation Help

If you ever need help coming up with a good complex password Linux has a terminal command for you called the `apg` command.

Here is an example of the command in use, Note: I *do not* suggest using one of these generated passwords this is just for clarity... 😀. The ` apg` command below uses the `-m 30` flag to generate a password of with a minimum of 30 characters. You will want to save this password in your password manager if you use one, or else make not of it somewhere obviously. You will need it again soon.

Example command and it`s output:

```bash  
$ apg -m 30
claHufipNilRoomvivjarnOccideb!
NugDivmidKicyenCidadyedIatmagg
tajthiHagToushkyetObFaGloolyey
ObdepDicEwjodthUbterposDedsOyn
stentaytDyriFinWitwughityidEv2
UjReynLongEchdoukCeictyabotout
```

##### Back to the nickname registration

Now that you have generated a few decent passwords choose one to use with the irc command from above and enter it into the channel window. It should look like this (obviously this is not my real password 😉):

```irc
/msg NickServ REGISTER YourSecureComplexPassword emailaddress@domain.tld
```

![NickServ Register command](/images/pidgin_aiu_ubuntu_club_channel_nickname_registration.png)

Your *direct message* to the *NickServ* irc account will open a new tab and window in Pidgin.

![NickServ Direct Message Window](/images/pidgin_nickserve_registration_window.png)

You should soon receive an email to the address you used to register. In that email will be a command you must cut and paste into the **NickServe** chat window. Or a link you can click in the browser. Check your Spam folder if necessary to find the email.

![NickServ Direct Message Window](/images/pidgin_aiu_ubuntu_club_channel_nickname_registration_verification.png)

NickServ will message you back with a message in the chat window like this:

```irc
(03:39:41 PM) NickServ: (notice) hepaestus has now been verified.
(03:39:41 PM) NickServ: (notice) Thank you for verifying your e-mail address! You have taken steps in ensuring that your registrations are not exploited.
(03:39:41 PM) NickServ: (notice) You have been given a default user cloak.
```

In order to make sure nobody else uses your nickname, next enter the irc command as follows:

```irc
/msg NickServ SET ENFORCE ON
```

You will see the following response:

```irc
(05:39:22 PM) NickServ: (notice) The ENFORCE flag has been set for account hepaestus.
```

**Congratulations** you now have a more permanent username on the Libre Chat Irc Server. And only you should be able to ues that nickname.

You can now enter your password into the Pidgin connection dialog so that you can connect to your account every time you run Pidgin.

In the Pidgin Buddy List window, Click the "Accounts" Menu, Click on the only entry you should have available for the Libre Irc server and save your password there. Also select the "Remember Password" checkbox for your convenience later when connecting.

![Save Your Password In Pidgin](/images/pidgin_add_account_basics_with_password_saved.png)

You can now disconnect from irc and reconnect to test your password and username registration.

#### Connecting To A Channel

To join a channel you can click the "Buddies" menu in the Pidgin window, select "Joins a Chat" and enter the club channel name: `#aiu_ubuntu_club`.

#### What other Channels are there?

You can used the "Room List" button, or the `/list` command in the chat window, to see the publicly available channel rooms on the server. There will be MANY of them and it can be overwhelming.

#### Always Joining the Club Channel

To always join the **#aiu_ubuntu_club** channel. In the "Pidgin Buddies" window, right click in on the club channel name, and select the "Auto Join" option.

### Conclusion

At this point you should be in the club channel. You should have a registered irc **nickname** on the Libre Chat server, a good complex password for your account. And you should be able able to auto join the club channel.

I hope this was helpful and informative.

Happy Chatting, hope to see you in the channel soon.

P.
