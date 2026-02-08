0:00
hey everyone welcome back to another video here on try hackney i am john and today we're going to be taking a look at the linux fundamentals
0:07
part three room power up your linux skills and get hands on with some common utilities that you're likely to use
0:12
day to day this room is the third and final room in the linux fundamental
0:19
series and with that being said let's go ahead and dive right into task one introduction welcome to part three and
Task 1: Introduction
0:26
the finale of the linux fundamentals module so far throughout the series you have got hands-on with some fundamental
0:33
concepts and use some important commands this room is going to showcase some useful utilities and
0:39
applications that you are likely to use day to day you're also going to advance your linux fuse skills by learning about
0:45
automation package management and service slash application logging let's proceed we'll go ahead and
0:51
mark this as completed and move into task 2 and deploy our machine
Task 2: Deploy Your Linux Machine
0:56
so i'm gonna go through this since we've already covered this in part two in order to proceed with this room we
1:02
need to start but the machine that's attached to this task and the information about that machine is going to appear at the top and then
1:08
we also want to shut the attack box with this blue button up here we'll go ahead and glaze through this
1:15
looks like we are going to be sshing into this machine with the credentials of try hack me and then a password of
1:20
try hack me so we'll work this as completed and i will pause the recording once the machine is up we will go ahead and
1:26
ssh into our target box and we're back so i've gone ahead and
1:32
let the machine load and then we have also pulled up a terminal here let's go and ssh into our target machine
1:39
now one note uh there is an ip address that will populate down here the try hack me rooms wherever you see
1:45
that machine ip that will be replaced once the box is actually live and it has that ip address assigned
1:50
and you can just see it in uh in line with the text and that was the case right here that
1:56
being said let's go ahead and ssh in with the credentials try hack me at 10 10 231
2:04
247 and make sure that you are not using my box ip this will not work for you you need to make sure that you're typing in the one
2:10
that you are targeting and there we go if you have any
2:15
difficulties with this please jump back to part two right at the beginning of that uh i go through how to uh
2:23
ssh into a machine like this into in further detail that being said let's go ahead and move
2:29
on to task three terminal text editors throughout the series so far we have
Task 3: Terminal Text Editors
2:35
only stored text and files using a combination of the echo command and the pipe operators
2:40
so a single greater than which is the redirection operator and then the pension operator double greater than this is an inefficient way
2:47
to handle data when you're working with files with multiple lines in the sorts introducing terminal text editors there
2:54
are a few options that you can use all with a variety of friendliness and utility this task is going to introduce
2:59
you to nano but also show you an alternative named vim which try hackman is a room dedicated to
3:05
this is worth checking out that room is very educational nano it's easy to get started with nano
3:12
to create or edit a file using nano we simply use the command nano and then the file name
3:17
replacing file name with the name of the file you wish to edit and if that file does not exist and you
3:23
have permissions to write that to that directory you can use nano and then the file that you want to create
3:28
for the file name and then as long as you save when you exit that file will be created
3:33
otherwise it will just either overwrite or start modifying whatever file you select as long as you have permissions to write
3:39
to it once we press enter to execute the command nano will launch
3:45
where we can just begin to start entering or modifying our text so here we can see that after running that
3:50
we are greeted with the nano text editor this is a little bit small on my screen however going through and playing with this you'll become very used to using nano
3:57
very quickly it's very intuitive and it's the text editor that i use pretty pretty regularly on the command line
4:04
that being said while we're going to go over nano it's worth having at least a minimum comfort
4:09
level with a couple of the other uh text editors just because nano won't always be installed and the other
4:15
editors are not too tricky to learn either that being said let's go ahead and move on you can navigate each line
4:21
using the up and down arrow keys or sort a new line using the enter key on your keyboard so very similar to
4:27
less and we'll be reviewing the man pages uh very very similar to that where we can navigate with the arrow keys and here
4:33
you can see we have a bunch of shortcuts here at the bottom nato has a few great features that are easy to remember
4:39
and covers uh the most general things you would want out of a text editor including searching for text which you
4:44
can see right here with the control w copying and pasting and you should be able to see
4:51
i'm not seeing it oh there we go right there jumping to a line number and then finding out what line number you're on
4:57
very basic things and they're very nice especially if you need to edit a program edit a script or you're just taking
5:02
notes in nano you can use these features of nano by pressing the ctrl key which is
5:07
represented as a carrot or an up arrow on linux and you can see that right here and a corresponding letter so for
5:14
example if we wanted to exit we would want to press ctrl and then x to exit nano
5:20
now one thing to note if you've modified a file it will prompt you to press y or n to confirm if you want to keep those
5:25
changes or discard them and you can see the exit command over here in the corner in case you ever
5:31
forget it let's talk briefly about vim vim is a much more advanced text editor
5:37
whilst you're not expected to know all advanced features it's helpful to mention it for powering up your linux skills and
5:43
you here you can see this is the basic vim text editor some of them's benefits albeit taking a
5:50
much longer time to become familiar with include customizability you can heavily
5:56
modify the keyboard shortcuts to be of your choosing i believe you might be able to do this in nano as well however vim it's just a
6:02
lot easier and generally speaking if you need advanced features you're probably going to moving on to using them anyways
6:08
syntax highlighting this is useful if you are writing or maintaining code making it a popular choice for software developers very common to
6:15
be using vim especially if you are in a developer environment and you are just remoted into whatever machine
6:21
is running your test web server if you want to try a sample change in your test environment
6:26
changing into vm is probably your best option vim works on all terminals where nano
6:31
may not be installed nano is not always installed vm will typically always be installed it's very rare to not have vm available
6:39
there are lots of resources such as cheat sheets and i recommend bookmarking this tutorials and sorts available for you to
6:45
use and again try hack me as a room just on vim i highly recommend going through this uh we've mentioned previously in part
6:52
two that there is a fine command room i recommend going through that and the vim room it they are both very helpful an expression
6:58
of the find command it was very insightful when i went through it create a file using nano let's go ahead and do that right now
7:04
so we'll do nano and then let's call it hello so here we have the nano text
7:11
editor very straightforward we saw this earlier in the task if i type something in here such as
7:17
hello world we can do control x and we can see that it wants just to confirm the changes that we've made to
7:24
the file and in this case since we can write to it we can write just press y and we save our file and we confirm
7:32
that the name of the file is going to be hello press enter and there we go we've exited
7:37
and if we run ls we can see that we have hello available there
7:42
and if we track it as well using file we can confirm that we created an ascii text file pretty cool
7:49
edit task 3 located in tri hackme's home directory using nano what is the flag let's do nano task
7:56
3 and we can see that our flag is thm text underscore editors
8:04
and there we go cool let's go ahead and close out of that and note because i didn't make any changes nano did not prompt me to
8:10
confirm those changes let's move on to task 4 general slash useful utilities
Task 4: General/Useful Utilities
8:20
downloading files a pretty fundamental feature of computing is the ability to transfer files for example you may want to download a
8:27
program a script or even a picture thankfully for us there are multiple ways in which we can retrieve these
8:32
files we're going to cover the use of wget this command allows us to download files from the web via http as if you were
8:40
accessing the file in your browser http is just the basic web protocol for
8:47
a website that's uh running without encryption you've probably interacted with a website like this before you
8:52
don't need to know too much about the actual web protocols just know that this is one way that websites can respond we see
9:00
the other way or the other major way i should say is https uh the s stands for
9:06
encryption so there is the ssl socket layer running there don't worry too much about that it's
9:12
outside of the scope of this room just know that that is there this is in clear text but it's
9:17
useful if you just want to download things we simply need to provide the address of the resource that we wish to download if
9:23
we want to download something in this manner for example if i wanted to download a file named myfile.txt
9:29
onto my machine assuming i knew the web address it is at it would look something like
9:35
this and you can see an example down below where we have wgent and then we have the file that we're actually going
9:41
to download that downloads the file to our current working directory so just wherever we're running this command from
9:47
transferring files from your host using scp via ssh secure copy or scp
9:54
is just that a means of securely copying files unlike the regular cp command this
10:00
command allows you to transfer files between two computers using the ssh protocol to provide both authentication and
10:06
encryption very very helpful and this is uh this may be overwhelming at first but i
10:12
promise you that the syntax on this is very intuitive once you've used it a couple times working on a model of source and
10:19
destination scp allows you to copy uh files and directories both to and from your current system and remote
10:26
systems as long as you have ssh access you can go through and copy files very cool and very straightforward
10:33
provided that we know usernames and passwords for a user on your current system and a user on the remote system
10:39
we can go ahead and copy files from our machine to a remote machine and here we can see that the command has
10:44
already been laid out in this table i'm gonna go ahead and walk through it in the full command down
10:49
below and let's break this down now first we have the command scp which specifies that we're using secure copy
10:56
we are copying a file from our computer here so the source is here this would be flipped
11:03
around if we wanted to grab this from a remote machine however we're grabbing something from our local machine named important.txt
11:09
and we're transferring it to a machine where we are logging into as ubuntu and then again note this is
11:16
the same syntax as ssh with the ip address here and then we have a con
11:22
with the actual location of where we're going to transfer that to so very straightforward think of this as
11:27
ssh and cp if they were combined together again if we wanted to transfer something from the
11:34
remote system to our local system it will be reversed and we can see that down here below where we have scp the command which is
11:41
just ssh and then the actual location of the file and then we're copying it to our current working directory
11:47
and having it named as notes note we can rename things as we copy again this is very straightforward and very similar to
11:54
what we saw with the cp command the normal copy command serving files from your host with web
12:00
ubuntu machines come pre-packaged with python 3. python helpfully provides a lightweight
12:06
and easy to use module called http server this module turns your computer into a quick and easy web server
12:12
that you can use to serve your own files but they can be downloaded by another computer using commands such as wget
12:18
and curl python 3's http server will serve the files in the directory
12:23
that you run the command from but this can be changed by providing options that can be found in the man pages simply all we need to do is run
12:30
python3 m for the module that we're going to run and then http dot server now note there's an extra
12:37
space here you don't need these two spaces it's just one space and even then python should just ignore
12:42
that extra space so running that will start the module and note that this will occupy your terminal because it's a running process
12:49
this is an example where having this running in the background can be very helpful especially if you want to work in one
12:54
terminal and you're not working with something like tmux tmux and other multitasking solutions
13:00
are again outside of the scope of this room however just know that they exist and there are other ways that you can accomplish these tasks
13:07
in the screenshot below we are serving from the directory called web server which is a single file named file
13:12
so we are in on this computer the web server directory in this user's home directory and then
13:18
we can see that there's this file file and then we run the python 3 server
13:24
or the python 3 web server rather and note that it searched by default on port 8000. you can specify this by using the dash
13:31
lowercase p switch and you can see more in the man page for this there's a bunch of different options and it's very very cool
13:38
by and large this is going to be one of your best friends as far as tools go especially if you are going further into
13:44
pen testing and need to transfer things to and from a remote machine now let's use wget to download the file
13:51
using the computer's ip address and the name of the file one flaw with this module is that you
13:56
have no way of indexing so you must know the exact name and location of the file that you wish to use
14:02
and the author talks a little bit about updog here this is actually what i use as well it is a very nice python
14:09
module outside of the scope of this room but i definitely recommend looking into this as it is incredibly useful just for file
14:16
transfers in general that being said here we have an example broken down we are running ls to confirm
14:22
that there's nothing in this current working directory of files and then we are running wgant this is on
14:27
our same host so we're just downloading something from one part of our machine to another but it's just an example and we specify
14:34
the full web url specifying that it is on port 3000 and that we want to or 8 000 rather
14:40
and that we want to pull the file named file we can see that it is in the process of
14:46
downloading it here and this will actually move as you are running this command so if
14:51
it's pretty big it will show a progress bar down here and it's nice it's very intuitive to use
14:57
once we've completed that we can see we've downloaded the file here in the screenshot above we can see that
15:02
the wget has successfully downloaded the file named file to our machine this request is logged by
15:08
simple http server much as any web shaver would which i have captured in the screenshot below and here you can see that this is
15:15
an example of the web server logs we saw a little bit of this in the linux fundamentals part 1 room
15:20
and you can see that that log is very much real that was i believe in apache 2 log however you can see an example of even
15:27
how this as a simple http server is able to actually do this
15:33
ensure that you were connected to the deployed instance we've gone ahead and done that we've ssh in if you have not i recommend
15:39
backtracking and making sure that you are asset your ssh into it now use python 3's
15:45
http server module to start a web server in the home directory of the try acme user on the deployed instance
15:51
let's go ahead and do that now so i've cleared the screen with control and l and we want to do python3 dash m
15:59
http.server and there we go again like i said this consumes your terminal so running this in the
16:04
background can be really helpful or running it in another tab which you can see up here however
16:11
let me go ahead and not kill my process there we go and i'm going to go ahead
16:18
and open up another tab like so we'll mark this as completed since we've gone ahead
16:24
and pulled that file or inserted the web server rather now we want to download a file hosted at
16:29
this address we can go ahead and do that now with wget
16:34
http and then 10 10 231
16:40
247 and then we need to do colon 8000 again
16:46
because this is running on port 8000 and we're going to grab the dot flag file
16:51
from flag.txt file and we're just downloading that to our current working directory and there we go it's pretty fast we can
16:59
see now if we do lstack l to show or ls attack a rather
17:07
and let me clear the screen we can see that we have this dot flag file now if we go ahead
17:13
and cat dot flag dot txt we can see that we have our flag for the web server which is thm
17:20
wget underscore web server and there we go create and download
17:27
files to further apply your learning so play around with this a little bit try uploading and downloading some files or downloading some files rather
17:34
it is good to get some practice with this and this is something that you will use very regularly so just keep that in mind
17:40
once you're done with that we'll go ahead and go back to our remote machine and use ctrl and c to interrupt that process and close it
17:47
out and again i've clicked the screen after that with control now let's go ahead and mark that as completed and move into task 5
17:54
processes 101
