Solving <https://www.hackthissite.org/>

## Basic

## 1.

> Basic test of your skills to see if you can do any of these 
> missions. Requirements: HTML

> This level is what we call "The Idiot Test", if you can't complete 
> it, don't give up on learning all you can, but, don't go begging to 
> someone else for the answer, thats one way to get you hated/made 
> fun of. Enter the password and you can continue.

https://www.hackthissite.org/missions/basic/1/

### Solution

View the pages code, and the password shall be revealed, it is in an
HTML comment.

## 2.

> A slightly more difficult challenge, involving an incomplete 
> password script. Requirements: Common sense.

> Network Security Sam set up a password protection script. He made 
> it load the real password from an unencrypted text file and compare 
> it to the password the user enters. However, he neglected to upload 
> the password file...

https://www.hackthissite.org/missions/basic/2/

### Solution

The password is an empty string, solved using common sense with help
of the challenges description.

## 3.

> Some intuition is needed to find the location of the hidden 
> password file. Requirements: Basic HTML knowledge

> This time Network Security Sam remembered to upload the password 
> file, but there were deeper problems than that.

https://www.hackthissite.org/missions/basic/3/

### Solution

If we inspect the HTML of the form we get:

```HTML
<form action="/missions/basic/3/index.php" method="post">
  <input type="hidden" name="file" value="password.php">
  <input type="password" name="password"><br><BR>
  <input type="submit" value="submit">
</form>
```

On the second line we see a hidden file input, it seems that the value
of this file is the path to a file on the server that contains the
__password__. Just navigate to the url.

## 4. 

> An email script has been set up, which sends the password to the 
> administrator. Requirements: HTML knowledge, an email address
>
> This time Sam hardcoded the password into the script. However, 
> the password is long and complex, and Sam is often forgetful. So 
> he wrote a script that would email his password to him 
> automatically in case he forgot. Here is the script:

https://www.hackthissite.org/missions/basic/4/

### Solution

If we inspect the HTML of the "Send password to Sam" button, we see
a form:

```HTML
<form action="/missions/basic/4/level4.php" method="post">
    <input type="hidden" name="to" value="sam@hackthissite.org">
	<input type="submit" value="Send password to Sam">
</form>
```

The first input is hidden and its value is a hardcoded email address.
We simply have to replace it with an email address we have access to
and the password will be sent to that address.
