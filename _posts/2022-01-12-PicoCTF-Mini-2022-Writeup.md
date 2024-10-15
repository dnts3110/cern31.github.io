---
title: "PicoCTF Mini 2022 Writeup"
image: 
    path: 'https://picoctf.org/img/logos/picoctf-logo-og.png'
date: 2022-01-12
categories: [CTF Jeopardy]
tags: [Web, MISC, Cryptography, General]
---

## Codebook
#### Question
![Screen Shot 2022-01-11 at 11 10 21 pm](https://user-images.githubusercontent.com/65474495/148940209-6f7deb95-8fcf-47a3-b1a4-384f6f0ce66b.png)

#### Solution
They required us to put these two files into a same directory, so I created a new directory called codebook and changed to this directory
> <img width="236" alt="Screen Shot 2022-01-12 at 1 02 43 am" src="https://user-images.githubusercontent.com/65474495/148956889-14d48035-16c6-4350-90c3-16ba520fd6e2.png">

Then I downloaded those two files using wget
> <img width="431" alt="Screen Shot 2022-01-12 at 1 05 44 am" src="https://user-images.githubusercontent.com/65474495/148957412-63fb40f6-557d-4ac1-a229-3da260ffd33c.png">
> <img width="480" alt="Screen Shot 2022-01-12 at 1 06 00 am" src="https://user-images.githubusercontent.com/65474495/148957462-3f9c18a1-75cd-4df7-bd3e-c114816ff093.png">

Then I ran the Python script code.py, which then gave the flag
> <img width="284" alt="Screen Shot 2022-01-12 at 1 07 36 am" src="https://user-images.githubusercontent.com/65474495/148957741-71a46b79-5c06-4077-ac1d-eeb048f60473.png">

#### Flag
> picoCTF{c0d3b00k_455157_8100c7c1}

## Glitch Cat
#### Question
![Screen Shot 2022-01-12 at 2 16 04 am](https://user-images.githubusercontent.com/65474495/148969480-b7430c66-f40a-4e99-a389-7e9160d3fffd.png)

#### Solution
Use nc to see what happen on nc saturn.picoctf.net 52026
> <img width="625" alt="Screen Shot 2022-01-12 at 2 19 07 am" src="https://user-images.githubusercontent.com/65474495/148970057-fcaa0441-2032-48fa-acba-6c54f40b829f.png">

These "chr(0x62)" looks like they are in hexademical, so I use this [website](https://www.rapidtables.com/convert/number/ascii-hex-bin-dec-converter.html) to convert those hex to [ASCII](https://en.wikipedia.org/wiki/ASCII), which gives the rest of the flag
> ![Screen Shot 2022-01-12 at 2 30 05 am](https://user-images.githubusercontent.com/65474495/148972003-04da595a-4431-447a-8dc9-7960c89a60a6.png)

#### Flag
> picoCTF{gl17ch_m3_n07_becf3861}

## HashingJobApp
#### Question
![Screen Shot 2022-01-12 at 2 48 05 am](https://user-images.githubusercontent.com/65474495/148975056-afc0ff1b-0d0b-4ebd-9f68-012bf6ddd739.png)

#### Solution
Use nc to see what happen on nc saturn.picoctf.net 65352
> <img width="585" alt="Screen Shot 2022-01-12 at 2 49 49 am" src="https://user-images.githubusercontent.com/65474495/148975426-33aa9de4-b699-40e2-8d91-9516d43a26ea.png">

It requires us to md5 hash the text "babies", so I use this website called CyberChef(https://gchq.github.io/CyberChef/), which give this result
> ![Screen Shot 2022-01-12 at 2 52 46 am](https://user-images.githubusercontent.com/65474495/148976014-7eebbc7f-3bdc-4de9-843c-7f7dc5ef1160.png)

> 8374d0764f1466e601c624254222ad53

Lets input this and see what happens
> <img width="625" alt="Screen Shot 2022-01-12 at 2 53 56 am" src="https://user-images.githubusercontent.com/65474495/148976188-054f7476-866e-4e64-b6ff-e45a6fbeb58f.png">
> So it seems like there is a timeout mechanic and it will random the text that is required to be hashed, :) so lets do everything above quickly and see if we can get the flag.

Do everything above for a second time, but quickly and see what happens
> <img width="625" alt="Screen Shot 2022-01-12 at 2 57 26 am" src="https://user-images.githubusercontent.com/65474495/148976769-31cdf24b-fe4f-4d97-b0fb-d1fbb058a9fa.png">

Interestingly, it requires us to do the md5 hash function for 3 times quickly before getting the flag

#### Flag
> picoCTF{4ppl1c4710n_r3c31v3d_674c1de2}

## PW-Crack-1
#### Question
![Screen Shot 2022-01-12 at 2 01 18 am](https://user-images.githubusercontent.com/65474495/148966925-b91863b5-8341-42a6-8bea-50c0b72a4387.png)

#### Solution
Use mkdir to create a directory and change to this directory to later download those two file using wget, to the same directory as required
> <img width="173" alt="Screen Shot 2022-01-12 at 2 04 24 am" src="https://user-images.githubusercontent.com/65474495/148967429-273b042e-d2a9-4af1-a9fe-5d2b5b88f42f.png">

> <img width="451" alt="Screen Shot 2022-01-12 at 2 04 51 am" src="https://user-images.githubusercontent.com/65474495/148967494-4618f9cf-235f-492b-a527-5b56f372be98.png">
> <img width="515" alt="Screen Shot 2022-01-12 at 2 05 14 am" src="https://user-images.githubusercontent.com/65474495/148967565-919f795b-0edd-45b3-8a1e-ee14d63e3ba7.png">

> <img width="267" alt="Screen Shot 2022-01-12 at 2 06 26 am" src="https://user-images.githubusercontent.com/65474495/148967748-edec1b4c-37fe-4112-b525-e46eb9124136.png">

Using nano to read that password checker file in Python
> <img width="230" alt="Screen Shot 2022-01-12 at 2 08 49 am" src="https://user-images.githubusercontent.com/65474495/148968118-5ec427db-9a31-4440-b17e-eb055a4e5f6d.png">


It seems that if we input "691d" then we can get the flag
> <img width="512" alt="Screen Shot 2022-01-12 at 2 08 26 am" src="https://user-images.githubusercontent.com/65474495/148968049-726d111c-5f4c-43ca-9619-e01e6448a3b9.png">


Then run this Python script to see if this is true
> <img width="365" alt="Screen Shot 2022-01-12 at 2 09 50 am" src="https://user-images.githubusercontent.com/65474495/148968314-223ff21f-fdef-41e1-8eaf-1c3bb1d6ec8b.png">

#### Flag
> picoCTF{545h_r1ng1ng_56891419}

## PW-Crack-2
#### Question
![Screen Shot 2022-01-12 at 2 33 06 am](https://user-images.githubusercontent.com/65474495/148972534-f903272f-2e59-44bb-8ce6-e8cdeeea6a37.png)


#### Solution
Use mkdir to create a directory and change to this directory to later download those two file using wget, to the same directory as required
> <img width="175" alt="Screen Shot 2022-01-12 at 2 35 40 am" src="https://user-images.githubusercontent.com/65474495/148972953-0912869e-d532-432b-805c-3d511ce55493.png">

> <img width="439" alt="Screen Shot 2022-01-12 at 2 36 39 am" src="https://user-images.githubusercontent.com/65474495/148973129-42975132-70d5-4127-9a6d-cddec34ff30c.png">

> <img width="522" alt="Screen Shot 2022-01-12 at 2 36 48 am" src="https://user-images.githubusercontent.com/65474495/148973156-f946947e-e530-4efa-9d4f-1be141ca9237.png">

> <img width="258" alt="Screen Shot 2022-01-12 at 2 38 20 am" src="https://user-images.githubusercontent.com/65474495/148973414-faaaca8e-e92c-456d-922d-c34b2361eeab.png">


Use nano to read that password checker file in Python
> <img width="244" alt="Screen Shot 2022-01-12 at 2 39 04 am" src="https://user-images.githubusercontent.com/65474495/148973552-637d1c12-d4ed-4f54-9551-3594b79f474b.png">

These "chr(0x34), etc" looks like they are in hexademical, so I use this [website](https://www.rapidtables.com/convert/number/ascii-hex-bin-dec-converter.html) to convert those hex to [ASCII](https://en.wikipedia.org/wiki/ASCII), which gives the password to get the flag.
> <img width="556" alt="Screen Shot 2022-01-12 at 2 40 48 am" src="https://user-images.githubusercontent.com/65474495/148973856-81a04d81-5949-4d96-b604-1b565f7069f8.png">

> ![Screen Shot 2022-01-12 at 2 41 43 am](https://user-images.githubusercontent.com/65474495/148974042-eca4d38c-03cc-475a-bf56-ba2178aec5b7.png)

The password to get the flag is 4ec9, run level2.py to get the flag
> <img width="370" alt="Screen Shot 2022-01-12 at 2 43 32 am" src="https://user-images.githubusercontent.com/65474495/148974336-d4189761-2847-4a2f-bbfd-b44036ec0706.png">

#### Flag
> picoCTF{tr45h_51ng1ng_9701e681}

## PW-Crack-3
#### Question
![Screen Shot 2022-01-12 at 3 11 08 pm](https://user-images.githubusercontent.com/65474495/149062533-bedd0e1e-8736-48d2-abd3-1bfeae40811b.png)

#### Solution
Simply try all 7 given password to see which is correct
> <img width="372" alt="Screen Shot 2022-01-12 at 3 11 19 pm" src="https://user-images.githubusercontent.com/65474495/149062549-97fae1e8-1dd0-4176-8a6e-20b541ff15cb.png">

#### Flag
> picoCTF{m45h_fl1ng1ng_6f98a49f}

## PW-Crack-4
#### Question
![Screen Shot 2022-01-12 at 3 28 16 pm](https://user-images.githubusercontent.com/65474495/149063884-f5d6eb70-d626-4b44-b4da-da82d6f612c0.png)

#### Solution
Looking at source code, it looked the same as the PW Crack 3's source code, the only difference was they gave us 100 strings to check which one is correct instead of 7
> <img width="577" alt="Screen Shot 2022-01-12 at 3 33 46 pm" src="https://user-images.githubusercontent.com/65474495/149064350-2d9b5964-233b-4fb7-a102-7e0063bd357b.png">

So now trying to input each of those strings will not be feasible. thus I edited the source code so that it will automatically try every input for us when the level4.py script run, this used a for loop to do that
> <img width="606" alt="Screen Shot 2022-01-12 at 4 19 13 pm" src="https://user-images.githubusercontent.com/65474495/149068485-a4d9f533-8a36-47ac-bca8-57f7db8a647b.png">
> <img width="598" alt="Screen Shot 2022-01-12 at 4 21 25 pm" src="https://user-images.githubusercontent.com/65474495/149068680-793b6f22-c1bb-45ba-b290-4a1601a27049.png">

#### Flag
> picoCTF{fl45h_5pr1ng1ng_89490f2d}

## PW-Crack-5
#### Question
![Screen Shot 2022-01-12 at 4 22 44 pm](https://user-images.githubusercontent.com/65474495/149068786-15771f88-ba28-43b5-b798-4b5db4021a55.png)


#### Solution
Looking at source code, it looked the same as the PW Crack 4's source code, the only difference was they gave us a txt file, which has a lot of strings, to check which one is correct instead of 100
> <img width="577" alt="Screen Shot 2022-01-12 at 3 33 46 pm" src="https://user-images.githubusercontent.com/65474495/149064350-2d9b5964-233b-4fb7-a102-7e0063bd357b.png">

So now besides using a for loop to automatically try every input for us when the level4.py script run, we also need to edit the code so that it will open and read that txt file appropriately, that is using open() to access these strings and strip() to trim the whitespace from them if any. 
> <img width="485" alt="Screen Shot 2022-01-12 at 4 36 10 pm" src="https://user-images.githubusercontent.com/65474495/149070007-50fdc67e-4464-403c-8167-097caad31624.png">
> <img width="533" alt="Screen Shot 2022-01-12 at 4 38 17 pm" src="https://user-images.githubusercontent.com/65474495/149070201-3693b557-3eb2-4b04-a9be-f75c6dd57f6c.png">

#### Flag
> picoCTF{h45h_sl1ng1ng_2f021ce9}

## Serpentine
#### Question
![Screen Shot 2022-01-12 at 3 02 01 am](https://user-images.githubusercontent.com/65474495/148977610-1aa86f34-d693-4a38-bc18-e8d8d26e6908.png)

#### Solution
Use wget to get this Python script
> <img width="623" alt="Screen Shot 2022-01-12 at 3 09 11 am" src="https://user-images.githubusercontent.com/65474495/148978817-da03174b-268d-4ef1-a1d0-67334d8f53fa.png">


When I tried to run this Python script, it recommended me to check the source code
> <img width="608" alt="Screen Shot 2022-01-12 at 3 10 13 am" src="https://user-images.githubusercontent.com/65474495/148978993-745c12f2-f842-41d4-9225-913ee53a4ccd.png">

Take a look at the source code, this part in the code looks like it can give us the flag, basically the flag is the result of the [XOR operation](https://en.wikipedia.org/wiki/Exclusive_or) between the variable "flag_enc" and the string "enkidu".
> <img width="685" alt="Screen Shot 2022-01-12 at 3 12 44 am" src="https://user-images.githubusercontent.com/65474495/148979438-87f451b5-9a9b-4521-8f32-27daa6284f0f.png">

#### Flag
> picoCTF{} 

## convertme.py
#### Question
![Screen Shot 2022-01-11 at 9 31 07 pm](https://user-images.githubusercontent.com/65474495/148927099-2c2ce454-6d40-431f-9a58-6da415042485.png)
#### Solution
Use [wget](https://www.gnu.org/software/wget/manual/wget.html) to get the given Python script 
> <img width="462" alt="Screen Shot 2022-01-11 at 10 02 44 pm" src="https://user-images.githubusercontent.com/65474495/148931196-7bf01667-687f-4773-bc86-04fe085d81a8.png">

Then it should stored at the directory you are at, use "ls" to check 
> <img width="539" alt="Screen Shot 2022-01-11 at 10 03 27 pm" src="https://user-images.githubusercontent.com/65474495/148931295-2d4bebcd-f653-4496-8274-f8d0e758fb58.png">

Run the Python file to see what it requires
> <img width="427" alt="Screen Shot 2022-01-11 at 10 04 14 pm" src="https://user-images.githubusercontent.com/65474495/148931393-15e58a8c-858e-4134-8eda-99d1f2133f19.png">

It requires us to convert a number from decimal base to binary base, so I use this website called CyberChef(https://gchq.github.io/CyberChef/) to help me do this
> ![Screen Shot 2022-01-11 at 10 43 09 pm](https://user-images.githubusercontent.com/65474495/148936724-fd7a3d13-fe5d-48b6-846f-99b57cb619ef.png)

Now I know the answer of this Python script, lets input this and take the flag :)
> <img width="544" alt="Screen Shot 2022-01-11 at 10 44 57 pm" src="https://user-images.githubusercontent.com/65474495/148936945-f0b58315-2dcc-462d-8d89-b8bb9a70650e.png">

#### Flag
> picoCTF{4ll_y0ur_b4535_e2a58836}

#### NOTE
I strongly recommend everyone new to CTF to use [CyberChef](https://gchq.github.io/CyberChef/) as it is easy to use and it has graphical interface. In the beginning I think this will be helpful, along the way you can find some nice software on github that can be used inside Kali Linux or something like that.
I found this websire while participating in MetaCTF, which is my first CTF and also my first ever documenting a [writeup](https://github.com/dnts3110/MetaCTF-2021-Write-up) for a CTF.

## fixme1.py
#### Question
![Screen Shot 2022-01-12 at 1 36 25 am](https://user-images.githubusercontent.com/65474495/148962774-66337961-ebb6-4d80-a150-a652bf8c434d.png)
#### Solution
Download the file and use Visual Studio Code that has installed Python Extension to open the file
> <img width="867" alt="Screen Shot 2022-01-12 at 1 39 16 am" src="https://user-images.githubusercontent.com/65474495/148963218-8edf20d3-9dc1-4413-a313-557c05b707bd.png">

The syntax error in this Python script is indentation
> <img width="450" alt="Screen Shot 2022-01-12 at 1 40 50 am" src="https://user-images.githubusercontent.com/65474495/148963455-82b6210f-dd99-4bf8-884e-60be4b723751.png">

The fix is going to be remove that indent/space and there should be no syntax error
> <img width="865" alt="Screen Shot 2022-01-12 at 1 41 59 am" src="https://user-images.githubusercontent.com/65474495/148963639-27381f14-d42f-4ccb-9ac2-7c1d8d2cef84.png">


Then run this Python script to see what happen next
> <img width="560" alt="Screen Shot 2022-01-12 at 1 43 33 am" src="https://user-images.githubusercontent.com/65474495/148963893-14eb3e5d-63e0-49f8-bfa0-1cf6ae69eeb1.png">

## Flag
> picoCTF{1nd3nt1ty_cr1515_09ee727a}

## fixme2.py
#### Question
![Screen Shot 2022-01-12 at 1 48 17 am](https://user-images.githubusercontent.com/65474495/148964761-604ebc90-38c4-4dd9-a39f-437b060d60f0.png)

#### Solution
Download the file and use Visual Studio Code that has installed Python Extension to open the file
> <img width="881" alt="Screen Shot 2022-01-12 at 1 48 57 am" src="https://user-images.githubusercontent.com/65474495/148964885-b4fd7e25-4a00-474d-b3d6-5fad3e4b4523.png">

The syntax error in this Python script is using operator in python
> <img width="430" alt="Screen Shot 2022-01-12 at 1 51 13 am" src="https://user-images.githubusercontent.com/65474495/148965280-89935051-a782-48df-ae80-38f9ba87edc2.png">


The fix is using "==" instead of "=" as "==" is an equality operator which would give us true or false based on the condition, while "=" is an assignment operator that is used when we want to assign a value to a variable
> <img width="408" alt="Screen Shot 2022-01-12 at 1 53 32 am" src="https://user-images.githubusercontent.com/65474495/148965655-69628e1b-94ca-49ea-b012-9dd3853248fc.png">



Then run this Python script to see what happen next
> <img width="547" alt="Screen Shot 2022-01-12 at 1 56 35 am" src="https://user-images.githubusercontent.com/65474495/148966180-dfb2cd7a-9587-450c-9ee2-4cc32f63dd8b.png">


#### Flag
> picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}

## ncme
#### Question 
![Screen Shot 2022-01-12 at 4 43 28 pm](https://user-images.githubusercontent.com/65474495/149070719-0ad7d40c-c3d2-478a-b6b0-7a0eeeb30be6.png)

#### Solution
Simply do as what the description said
> <img width="271" alt="Screen Shot 2022-01-12 at 4 43 54 pm" src="https://user-images.githubusercontent.com/65474495/149070749-f2c8c3f6-3c98-4d6f-bfda-273a01655309.png">

#### Flag
> picoCTF{s4n1ty_c4t}

## runme.py
#### Question 
![Screen Shot 2022-01-12 at 4 41 01 pm](https://user-images.githubusercontent.com/65474495/149070479-73427733-f9ef-41c5-bd9c-4b99115be83e.png)

#### Solution
Simply do as what the description says
> <img width="626" alt="Screen Shot 2022-01-12 at 4 41 39 pm" src="https://user-images.githubusercontent.com/65474495/149070532-3c92900d-1082-4265-9d3e-25571aca12f2.png">
> <img width="236" alt="Screen Shot 2022-01-12 at 4 42 06 pm" src="https://user-images.githubusercontent.com/65474495/149070585-8cd1a7bd-dc60-46b0-afc4-d9e1787b8cbd.png">

#### Flag
> picoCTF{run_s4n1ty_run}






