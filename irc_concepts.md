# IRC 

The godfather of all internet communications is IRC, or "Internet Relay Chat". IMO all the other internet protocols are basically dressed up versions of IRC. On Irc you can create private or public "rooms" where you can send instant messages to other members of the "room". You can also have direct connections between clients for singluar private conversations that. 

In Irc lingo these "rooms" are called **channels**.

## Irc Network / Server

We will use the public irc server called [Libera Chat](https://libera.chat/). One issue with Libera Chat that I noticed is that you cannot connect form the TOR network. If you are using a regular Ubuntu/Linux installation this should not be an issue. It you are using Tails Linux, by default it uses the TOR network, which you will have to disable first in order to *initially* connect to Libera Chat and set up an account. Fore more info on using TOR to connect see the [TOR Guide Entry](https://libera.chat/guides/connect#accessing-liberachat-via-tor)

To connect to the server you need to use the server address and port number. The address you will need is `irc.libera.chat`. Irc typically runs on port number `6697`. In Japan you might get better performance using the East Asia specific server `irc.ea.libera.chat`. In Australia and New Zealand	you can try `irc.au.libera.chat`

For more information on Libera Chat, see these very helpful webpages:

* https://libera.chat/guides/
* https://libera.chat/guides/basics
* https://libera.chat/guides/faq

You want you could just read those pages and skip to the the [Pidgin Installation](#the-pidgin-irc-client) section here but I will summarize some of the more salient points. :)

## Irc Clients

There are myriad IRC clients in the open source world. For the purposes of this tutorial We will be discussing [Pidgin](https://pidgin.im/). 

* Pidgin Website: https://pidgin.im/

There are even several terminal based irc clients if you are so enclined. Here are some examples:

* [glirc](https://hackage.haskell.org/package/glirc#readme)
* [irssi](https://irssi.org/)

If you want more see this list of pretty much every known ircV3 compliant clients:

* [https://ircv3.net/software/clients](https://ircv3.net/software/clients)


### The Pidgin Messageing Client

Pidgin is a messaging client that can connect to many different messaging protocols. This document is focused on the irc protocol and thus we will set up Pidgin for irc usage.

#### Command Line Installation:

This is probably the easiest install despite it using the command line.

Open a terminal/console window and at the command line type to 2 following commands. You will be prompted to enter your password to authhorize the installation.

```bash
sudo apt update
sudo apt install pidgin -y
```

After you enter your password and hit enter, you will see some output and eventually it will stop. At this point Pidgin should be installed and you should see it in your programs menu. 

#### Ubuntu Gui Installation:

In the Ubuntu Software installation client if you search for "Pidgin" you will likely find two options. They seem like they are slightly different. From what I can tell you want the **Pidgin "Instant Messaging Client"** rather than the *Pidgin Internet Messenger*. After you select the appropriate program and click install, you will be prompted for your password and the program will be installed. It should now be visible in your program menu.

#### Pidgin Set Up

When you start pidgin you will see the Add a network dialog window:

![Add Dialog](/images/pidgin_startup_add_dialog.png)

Click the **Add** button.

![Add Account Basic](/images/pidgin_add_account_basics.png)

In the basic tab: Set the Protocol to **irc**. Enter your preferred **username**, this will be seen by all other users. And then set your preferred server. The **Local Ident** is what your own username name will look like to yourself in the channel window. No Password is entered at this time. You may leave the Local Alias option blank as well. 

![Add Account Advanced](/images/pidgin_add_account_advanced.png)

In the advanced tab: Make sure Port is set to `6697`. For now do *not* check the "Use SSL" checkbox. Once we have set up a password on the irc server you will be able to use SSL so that your communications are encrypted. 

Click the "Save" button and the dialog will close. You will then see the empty and somewhat confusing "Pidgin Buddy List".

![Pidgin Buddy List](/images/pidgin_buddy_list_01.png)

Wait a few moments for Pidgin to connect to the irc server. A this point you may see a Connection Error" is so make sure you have followed all the steps as described above. 

At some point Pidgin will connect and show the "Available" status in the Buddy List.

![Pidgin Connection with Available Status](/images/pidgin_buddy_list_02.png)

Congratulations!! You are now connected to the irc server. You can now click the "Buddies" Menu item and Select "Join A Chat" from the menu.

You will no see the "Join a Chat" dialog screen.

![Join a Chat Dialog](/images/pidgin_join_a_chat_dialog.png)

In the Channel Box enter "#aiu_ubuntu_club". Make sure include the `#` sign. All irc channel names start with a `#` sign. 

![#aiu_ubuntu_club channel](/images/pidgin_aiu_ubuntu_club_channel_window.png)

You have now joined your first irc channel. You will see your username in the right hand panel of the window. The topmost name is the name of the **channel admin**. If you are the channel admin you might be in the wrong chat room. Check your channel name spelling. If you see my name *hepaestus* as an admin you are in the correct channel. I have entered some irc command to make create a more permanent non-ephemeral channel. 

On irc anyone can create a channel, you will be the owner of the channel **while you remain connected** and as long as no one else has started a channel with the same name. If you want to have a *more* permanent username and password, or a *more* permanent channel you need to use some magic irc commands. Which I will discuss [momentarily](#irc-commands).

You are now connected to the irc server and have entered a chat channel. You can not begin chatting with other users. Try saying hello and interacting with your fellow irc channel members.

You **could** stop here and be done. If you do your entire presence on irc will be ephemeral. No usernames will be saved, you don't need a password to connect. You do not *own* your username any one can use *your* name after you disconnect. Your channels that you create will also be ephemeral and open to the irc public at large.

### Irc Commands

In order to setup your account on the irc server you will have to enter a few commands directed to the server itself. You do this in the channel chat window itself by directing your chats to the server controller called **NickServe**.

#### Irc User Registration

For a complete description of this topic you can see the [Libre Chat Nickname Registration Guide](https://libera.chat/guides/registration). 

I will continue to summarize and hopefully simplify this here.

##### Registering Your Nickname

To create a less ephemeral irc presence you will first need to register your nickname.

In ANY chat window enter the following command.

```irc
/msg NickServ REGISTER YourPassword youremail@example.com
```

If you need help coming up with a good complex password Linux has a command for you called the `apg` command.

Here is an example of the command in use, I *do not* suggest using one of these generated passwords this is just for clarity... :). This command below uses the `-m 30` flag to generate a password of 30 characters. You will want to save this password in your password manager if you use one, or else make not of it somewhere obviously. You will need it again soon.

```bash  
$ apg -m 30
claHufipNilRoomvivjarnOccideb!
NugDivmidKicyenCidadyedIatmagg
tajthiHagToushkyetObFaGloolyey
ObdepDicEwjodthUbterposDedsOyn
stentaytDyriFinWitwughityidEv2
UjReynLongEchdoukCeictyabotout
```

Now that you have generated a few decent passwords choose one to use with the irc command from above and enter it into the channel window. It should look like this (obviously this is not my real password 😉):

![NickServe Register command](/images/pidgin_aiu_ubuntu_club_channel_nickname_registration.png)

Your *direct message* to the *NickServe* irc account will open a new tab and window in Pidgin.

![NickServe Direct Message Window](/images/pidgin_NickServe_registration_window.png)

You should soon receive an email to the address you used to register. In that email will be a command you must cut and paste into the **NickServe** chat window.

![NickServe Direct Message Window](/images/pidgin_aiu_ubuntu_club_channel_nickname_registration_verification.png)

NickServe will message you back with a message like this:

```irc
(03:39:41 PM) NickServ: (notice) hepaestus has now been verified.
(03:39:41 PM) NickServ: (notice) Thank you for verifying your e-mail address! You have taken steps in ensuring that your registrations are not exploited.
(03:39:41 PM) NickServ: (notice) You have been given a default user cloak.
```

**Congratulations** you now have a more permanent username on the Libre Chat Irc Server.

You can now enter your password into the Pidgin connection dialog so that you can connect to your account every time you run Pidgin.

In the Pidgin Buddy List window, Click the "Accounts" Menu, Click on the only entry you should have available for the Libre irc server and save your password there. Also select the "Remember Password" checkbox for your convenience later when connecting.

![Save Your Password In Pidgin](/images/pidgin_add_account_basics_with_password_saved.png)

You can now disconnect from irc and reconnect to test your password and username registration.

