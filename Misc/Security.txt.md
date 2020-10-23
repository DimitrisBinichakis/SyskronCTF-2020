### CHALLENGE PROMPT :

The security.txt draft got updated (https://tools.ietf.org/html/draft-foudil-securitytxt-10).

Is Senork's file still up-to-date? https://www.senork.de/.well-known/security.txt

------------------------------------------------------------------------------------

Our first link ( https://tools.ietf.org/html/draft-foudil-securitytxt-10 ) takes us to a manual , 
which " *defines a format ("security.txt") to help organizations describe their vulnerability
disclosure practices to make it easier for researchers to report vulnerabilities.* "

Here's a snipet of the first page of the document , it's 26 pages in total and goes through 
a lot of different things .

![Screenshot_2020-10-23 draft-foudil-securitytxt-10 - A File Format to Aid in Security Vulnerability Disclosure](https://user-images.githubusercontent.com/73142671/96948571-aa7ca700-14ee-11eb-818f-9d31b3064a03.png)

Our second link , ( https://www.senork.de/.well-known/security.txt ) takes us to a simple text only site 
as shown below .

![Screenshot_2020-10-23 https www senork de](https://user-images.githubusercontent.com/73142671/96948885-44445400-14ef-11eb-8fd0-d13c327c9b85.png)

Useful information we can extract from the above site is a PGP public key block , from the 
link below . 

![Screenshot_2020-10-23 https www senork de(1)](https://user-images.githubusercontent.com/73142671/96948935-6c33b780-14ef-11eb-8737-5a529c58bd7e.png)

Clicking on https://www.senork.de/openpgp.asc takes us to the PGP key . 


![Screenshot_2020-10-23 https www senork de(2)](https://user-images.githubusercontent.com/73142671/96949177-efeda400-14ef-11eb-844e-69a88e210bda.png)

We created a file called *pubkey.asc* in our own home directory , and pasted the
the PGP public key block into it . 

We need to try to extract the PGP keyid from our public key file , pubkey.asc .
A relevant Stack Overflow post shows a way to do it .
https://security.stackexchange.com/questions/43348/extracting-the-pgp-keyid-from-the-public-key-file

Running

  > gpg --dry-run --import pubkey.asc
  
outputs "*gpg: Total number processed: 1*"

Then , with the following command ,

  > gpg --import pubkey.asc 

we get this output .
  
![2020-10-23_05-39](https://user-images.githubusercontent.com/73142671/96950093-3217e500-14f2-11eb-96e0-8558037f1494.png) 


The flag is : **syskronCTF{Wh0-put3-flag3-1nto-0penPGP-key3???}**
  
  
  
  
  
  
  
