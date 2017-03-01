Davids-MacBook-Pro:homework davidbrandt$ cd command-line-mystery/
Davids-MacBook-Pro:command-line-mystery davidbrandt$ ls -a
.   .git    hint1   hint3   hint5   hint7   instructions  readme.md
..    cheatsheet.md hint2   hint4   hint6   hint8   mystery   solution.md
Davids-MacBook-Pro:command-line-mystery davidbrandt$ cat instructions
.OOOOOOOOOOOOOOO @@                                   @@ OOOOOOOOOOOOOOOO.
OOOOOOOOOOOOOOOO @@                                    @@ OOOOOOOOOOOOOOOO
OOOOOOOOOO'''''' @@                                    @@ ```````OOOOOOOOO
OOOOO'' aaa@@@@@@@@@@@@@@@@@@@@"""                   """""""""@@aaaa `OOOO
OOOOO,""""@@@@@@@@@@@@@@""""                                     a@"" OOOA
OOOOOOOOOoooooo,                                            |OOoooooOOOOOS
OOOOOOOOOOOOOOOOo,                                          |OOOOOOOOOOOOC
OOOOOOOOOOOOOOOOOO                                         ,|OOOOOOOOOOOOI
OOOOOOOOOOOOOOOOOO @          THE                          |OOOOOOOOOOOOOI
OOOOOOOOOOOOOOOOO'@           COMMAND                      OOOOOOOOOOOOOOb
OOOOOOOOOOOOOOO'a'            LINE                         |OOOOOOOOOOOOOy
OOOOOOOOOOOOOO''              MURDERS                      aa`OOOOOOOOOOOP
OOOOOOOOOOOOOOb,..                                          `@aa``OOOOOOOh
OOOOOOOOOOOOOOOOOOo                                           `@@@aa OOOOo
OOOOOOOOOOOOOOOOOOO|                                             @@@ OOOOe
OOOOOOOOOOOOOOOOOOO@                               aaaaaaa       @@',OOOOn
OOOOOOOOOOOOOOOOOOO@                        aaa@@@@@@@@""        @@ OOOOOi
OOOOOOOOOO~~ aaaaaa"a                 aaa@@@@@@@@@@""            @@ OOOOOx
OOOOOO aaaa@"""""""" ""            @@@@@@@@@@@@""               @@@|`OOOO'
OOOOOOOo`@@a                  aa@@  @@@@@@@""         a@        @@@@ OOOO9
OOOOOOO'  `@@a               @@a@@   @@""           a@@   a     |@@@ OOOO3
`OOOO'       `@    aa@@       aaa"""          @a        a@     a@@@',OOOO'


There's been a murder in Terminal City, and TCPD needs your help.

To figure out whodunit, go to the "mystery" sub-directory and start working from there.

You'll want to start by collecting all the clues at the crime scene (the "crimescene" file).

The officers on the scene are pretty meticulous, so they've written down EVERYTHING in their officer reports.

Fortunately the sergeant went through and marked the real clues with the word "CLUE" in all caps.

If you get stuck, open one of the hint files (from the Command Line, type "cat hint1", "cat hint2", etc.).

For tips on getting started with the Command Line, open "cheatsheet.md".

Don't use a text editor to view any files except "readme.md" and "cheatsheet.md".

Davids-MacBook-Pro:mystery davidbrandt$ grep -R "CLUE" crimescene
crimescene:CLUE: Footage from an ATM security camera is blurry but shows that the perpetrator is a tall male, at least 6'.
crimescene:CLUE: Found a wallet believed to belong to the killer: no ID, just loose change, and membership cards for AAA, Delta SkyMiles, the local library, and the Museum of Bash History. The cards are totally untraceable and have no name, for some reason.
crimescene:CLUE: Questioned the barista at the local coffee shop. He said a woman left right before they heard the shots. The name on her latte was Annabel, she had blond spiky hair and a New Zealand accent.


Davids-MacBook-Pro:mystery davidbrandt$ grep -R "AAA" interviews
interviews/interview-290346:Is a SkyMiles, TCPL, Museum of Bash History, and AAA member.

Davids-MacBook-Pro:interviews davidbrandt$ cat interview-290346
Drives a similar car to the description.

Is a SkyMiles, TCPL, Museum of Bash History, and AAA member.

Bostock is 6' 4", easily tall enough to match the camera footage.

However, upon questioning, Bostock can prove that he was out of town on the morning of the murder, multiple witnesses and credit card transactions confirm.

Davids-MacBook-Pro:mystery davidbrandt$ grep -R "Bostock" *
interviews/interview-290346:Bostock is 6' 4", easily tall enough to match the camera footage.
interviews/interview-290346:However, upon questioning, Bostock can prove that he was out of town on the morning of the murder, multiple witnesses and credit card transactions confirm.
memberships/AAA:Mike Bostock
memberships/Delta_SkyMiles:Mike Bostock
memberships/Museum_of_Bash_History:Mike Bostock
memberships/Terminal_City_Library:Mike Bostock
people:Mike Bostock M 45  Senders Court, line 287
vehicles:Owner: Mike Bostock

avids-MacBook-Pro:mystery davidbrandt$ grep -R "Bostock" vehicles
vehicles:Owner: Mike Bostock

Davids-MacBook-Pro:command-line-mystery davidbrandt$ cat hint1
Try poking around what's in a file by using the 'head' command:

  head -n 20 people

This will show you the first 20 lines of the 'people' file.Davids-MacBook-Pro:command-line-mystery davidbrandt$ cat hint2
Try using grep to search for the clues in the crimescene file:

  grep "CLUE" crimesceneDavids-MacBook-Pro:command-line-mystery davidbrandt$ cat hint3
In order to track down our potential witness, we need to figure out where she
lives.

Try using 'head' on some of the files like 'people' and 'vehicles' and see where we might find that.

Davids-MacBook-Pro:mystery davidbrandt$ head -n 20 people
***************
To go to the street someone lives on, use the file
for that street name in the 'streets' subdirectory.
To knock on their door and investigate, read the line number
they live on from the file.  If a line looks like gibberish, you're at the wrong house.
***************

NAME  GENDER  AGE ADDRESS
Alicia Fuentes  F 48  Walton Street, line 433
Jo-Ting Losev F 46  Hemenway Street, line 390
Elena Edmonds F 58  Elmwood Avenue, line 123
Naydene Cabral  F 46  Winthrop Street, line 454
Dato Rosengren  M 22  Mystic Street, line 477
Fernanda Serrano  F 37  Redlands Road, line 392
Emiliano Wenk M 90  Paulding Street, line 490
Larry Lapin M 71  Atwill Road, line 298
Jakub Gondos  M 61  Mitchell Street, line 187
Derek Kazanin M 55  Tennis Road, line 440
Jens Tuimalealiifano  M 83  Rockwood Street, line 205
Nikola Kadhi  M 75  Glenville Avenue, line 226

Davids-MacBook-Pro:mystery davidbrandt$ grep -R "Annabel" people
people:Annabel Sun  F 26  Hart Place, line 40
people:Oluwasegun Annabel M 37  Mattapan Street, line 173
people:Annabel Church F 38  Buckingham Place, line 179
people:Annabel Fuglsang M 40  Haley Street, line 176

Davids-MacBook-Pro:mystery davidbrandt$ grep -R "Annabel" memberships
memberships/AAA:Annabel Church
memberships/AAdvantage:Annabel Fuglsang
memberships/AAdvantage:Annabel Church
memberships/Fitness_Galaxy:Oluwasegun Annabel
memberships/Fitness_Galaxy:Annabel Church
memberships/Museum_of_Bash_History:Annabel Church
memberships/Museum_of_Bash_History:Oluwasegun Annabel
memberships/REI:Annabel Church
memberships/Rotary_Club:Annabel Sun
memberships/Rotary_Club:Annabel Fuglsang
memberships/Rotary_Club:Annabel Church

Davids-MacBook-Pro:command-line-mystery davidbrandt$ cat hint5
"Interview" the two possible witnesses by reading the correct line from the streets they live on:

  head -n 173 streets/Mattapan_Street | tail -n 1

This will give you just line 173 of Mattapan street, because it will take first 173 lines, and then take
the last line from those.

Davids-MacBook-Pro:mystery davidbrandt$ head -n 173 streets/Mattapan_Street | tail -n 1
SEE INTERVIEW #9437737

Davids-MacBook-Pro:interviews davidbrandt$ cat interview-9437737
Doesn't appear to be the witness from the cafe, who is female.

Davids-MacBook-Pro:mystery davidbrandt$ less +40 Hart_Place

SEE INTERVIEW #47246024

Davids-MacBook-Pro:mystery davidbrandt$ cd interviews
Davids-MacBook-Pro:interviews davidbrandt$ cat interview-47246024
Ms. Sun has brown hair and is not from New Zealand.  Not the witness from the cafe.

Davids-MacBook-Pro:interviews davidbrandt$ less +179 Buckingham_Place

SEE INTERVIEW #699607

Davids-MacBook-Pro:interviews davidbrandt$ cat interview-699607
Interviewed Ms. Church at 2:04 pm.  Witness stated that she did not see anyone she could identify as the shooter, that she ran away as soon as the shots were fired.

However, she reports seeing the car that fled the scene.  Describes it as a blue Honda, with a license plate that starts with "L337" and ends with "9"

// Annabel Church is the witness who ran.

Davids-MacBook-Pro:mystery davidbrandt$ grep -A5 "L337" *
grep: interviews: Is a directory
grep: memberships: Is a directory
grep: streets: Is a directory
vehicles:License Plate L337ZR9
vehicles-Make: Honda
vehicles-Color: Red
vehicles-Owner: Katie Park
vehicles-Height: 6'2"
vehicles-Weight: 189 lbs
--
vehicles:License Plate L337P89
vehicles-Make: Honda
vehicles-Color: Teal
vehicles-Owner: Mike Bostock
vehicles-Height: 6'4"
vehicles-Weight: 173 lbs
--
vehicles:License Plate L337GX9
vehicles-Make: Mazda
vehicles-Color: Orange
vehicles-Owner: John Keefe
vehicles-Height: 6'4"
vehicles-Weight: 185 lbs
--
vehicles:License Plate L337QE9
vehicles-Make: Honda
vehicles-Color: Blue
vehicles-Owner: Erika Owens
vehicles-Height: 6'5"
vehicles-Weight: 220 lbs
--
vehicles:License Plate L337GB9
vehicles-Make: Toyota
vehicles-Color: Blue
vehicles-Owner: Matt Waite
vehicles-Height: 6'1"
vehicles-Weight: 190 lbs
--
vehicles:License Plate L337OI9
vehicles-Make: Jaguar
vehicles-Color: Blue
vehicles-Owner: Brian Boyer
vehicles-Height: 6'6"
vehicles-Weight: 201 lbs
--
vehicles:License Plate L337X19
vehicles-Make: Fiat
vehicles-Color: Blue
vehicles-Owner: Al Shaw
vehicles-Height: 6'5"
vehicles-Weight: 240 lbs
--
vehicles:License Plate L337539
vehicles-Make: Honda
vehicles-Color: Blue
vehicles-Owner: Aron Pilhofer
vehicles-Height: 5'3"
vehicles-Weight: 198 lbs
--
vehicles:License Plate L3373U9
vehicles-Make: Ford
vehicles-Color: Blue
vehicles-Owner: Miranda Mulligan
vehicles-Height: 6'6"
vehicles-Weight: 156 lbs
--
vehicles:License Plate L337369
vehicles-Make: Honda
vehicles-Color: Blue
vehicles-Owner: Heather Billings
vehicles-Height: 5'2"
vehicles-Weight: 244 lbs
--
vehicles:License Plate L337DV9
vehicles-Make: Honda
vehicles-Color: Blue
vehicles-Owner: Joe Germuska
vehicles-Height: 6'2"
vehicles-Weight: 164 lbs
--
vehicles:License Plate L3375A9
vehicles-Make: Honda
vehicles-Color: Blue
vehicles-Owner: Jeremy Bowers
vehicles-Height: 6'1"
vehicles-Weight: 204 lbs
--
vehicles:License Plate L337WR9
vehicles-Make: Honda
vehicles-Color: Blue
vehicles-Owner: Jacqui Maher
vehicles-Height: 6'2"
vehicles-Weight: 130 lbs

Davids-MacBook-Pro:mystery davidbrandt$ grep Germuska *
grep: interviews: Is a directory
grep: memberships: Is a directory
people:Joe Germuska M 65  Plainfield Street, line 275
grep: streets: Is a directory
vehicles:Owner: Joe Germuska

Davids-MacBook-Pro:mystery davidbrandt$ grep Bowers *
grep: interviews: Is a directory
grep: memberships: Is a directory
people:Jeremy Bowers  M 34  Dunstable Road, line 284
grep: streets: Is a directory
vehicles:Owner: Jeremy Bowers

Davids-MacBook-Pro:streets davidbrandt$ less +275 Plainfield_Street
SEE INTERVIEW #29741223

Davids-MacBook-Pro:streets davidbrandt$ less +284 Dunstable_Road
SEE INTERVIEW #9620713

Davids-MacBook-Pro:interviews davidbrandt$ cat interview-29741223
Should not be considered a suspect, has no SkyMiles membership and has never been a member of the Museum of Bash History.

Davids-MacBook-Pro:interviews davidbrandt$ cat interview-9620713
Home appears to be empty, no answer at the door.

After questioning neighbors, appears that the occupant may have left for a trip recently.

Considered a suspect until proven otherwise, but would have to eliminate other suspects to confirm.

// All evidence leads to Jeremy Bowers as the killer.
