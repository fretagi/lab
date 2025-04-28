Start writing today. Use the button below to create a Substack of your own

[Start a Substack](https://substack.com/refer/fernandoretagi?utm_source=substack&utm_context=post&utm_content=162281230&utm_campaign=writer_referral_button)

In order for this to happen you need to set up SSH key pairs. These two files that make our key pairs will be generated in the .ssh folder of you home user account.

The public key with the extension .pub will have to be put on the GitHub server and the other key file will reside on your computer.

Generating the keys:

The first thing you have to do is to navidate to your .ssh folder of your home account (cd ~/.ssh) or make one (mkdir ~/.ssh)

/home/fretagi/.ssh $

Once into this directory use ssh-keygen command to create the files.

ssh-keygen -t ed25519 -C "youruser@whaterver.com" ---> this is what going to create the key-pair files for us.

Them the above command is going to prompt you for the file name for this key, you could either accept the defaults or insert a descriptive name to identify the key pair.

Please note that if you created SSH keys previously, ssh-keygen may ask you to rewrite another key, in which case we recommend creating a custom-named SSH key. To do so, type the default file location and replace id_ALGORITHM with your custom key name.

The next step will ask you for the passphrase for this key, you could either insert one, or leave it blank. Them will ask you to confirm that passphrase, you hit enter again, them you should a confirmation the the key-pairs files were generated.

The contents of the .ssh directory will now have:

fretagi@ubuntu24:~/.ssh$ ls -al

total 24

drwx------ 2 fretagi fretagi 4096 Apr 11 17:56 .

drwxr-x--- 25 fretagi fretagi 4096 Apr 19 23:06 ..

\-rw------- 1 fretagi fretagi 0 Feb 28 16:55 authorized_keys

\-rw------- 1 fretagi fretagi 419 Mar 1 16:06 id_ed25519

\-rw-r--r-- 1 fretagi fretagi 107 Mar 1 16:06 id_ed25519.pub

\-rw------- 1 fretagi fretagi 1956 Apr 11 17:56 known_hosts

\-rw------- 1 fretagi fretagi 1120 Apr 11 17:56 known_hosts.old

fretagi@ubuntu24:~/.ssh$

You will now see two new files name "id_ed25519" and "id_ed25519.pub", the first one is the private key that will be sitting on your computer, and the corresponding public key with the same name, but with extension .pub.

The next step is to take that public key and put it into the GitHub server.

Copying the public key to the GitHub server:

So now we switch to your GitHub account, goto settings, and them you will find an option for "SSH and GPG Keys", them find a button for new ssh-key, them we will gonna fill the information for these keys, the first thing is put title, for key type leave as Authentication key, and for key itself you will have to go back to your terminal and copy the contents of the public key using the cat command:

fretagi@ubuntu24:~/.ssh$ cat id_ed25519.pub

ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIDxxf4MMJzt8iIaV5b1rrB9OVagIXo811HOBRdVMTuNn fernando.retagi@gmail.com

fretagi@ubuntu24:~/.ssh$

starting with ssh-ed25519, and ending with the email address, them switch the GitHub web page and paste the contents into the key box, and them we add that ssh key with the appropriate button. And that's it really.

Testing:

You could go back to terminal and check if the functionality works by typing:

ssh -T git@github.com

fretagi@ubuntu24:~/.ssh$ ssh -T git@github.com

Hi fretagi! You've successfully authenticated, but GitHub does not provide shell access.

fretagi@ubuntu24:~/.ssh$
