Download Link: https://assignmentchef.com/product/solved-cs2124-homework-5-dynamic-memory
<br>
<strong>Focus</strong>

<ul>

 <li>Dynamic memory</li>

</ul>

<strong>Problem:</strong>

Building on previous assignments, we will be reading a file of commands to create Nobles and Warriors, and sending them off to battle.

Key differences:

<ul>

 <li>Each time a warrior or a noble is defined, we will create it on the heap.</li>

 <li>We will keep track of the nobles in a vector of pointers to nobles.</li>

 <li>We will keep track of <em>all warriors</em>using a vector of pointers to warriors.</li>

</ul>

The input file will be named “nobleWarriors.txt”.

<strong>Commands</strong>

<ul>

 <li>Create a Noble on the heap.</li>

 <li>Create a Warrior on the heap.</li>

 <li>Call the Noble’s hire method.</li>

 <li>Call the Noble’s fire method.</li>

 <li>Call the Noble’s battle method.</li>

 <li>The status command shows the nobles, together with their armies, as we did previously. In addition, it will show separately the warriors who do not currentle have a employer</li>

 <li>Clear out all the nobles and warriors that were created.</li>

</ul>

Our application is going to rely on each Noble having a unique name and each Warrior having a unique name. Otherwise, how would we be sure who we were hiring (or firing). Note that this is <u>not</u> a requirement of the Noble and Warrior classes themselves, just of this particular <em>use</em> of them, i.e. our application.

Whenever you are displaying a Noble or a Warrior, you will <u>use</u> the <strong>output operator</strong> for the class.

<strong>Handle errors!</strong>

Previously we promised that all of the commands we gave you the input would be valid. Now we would like you to take some responsibility for checking the input. First, we still guarantee that the <u>format</u> of the file will be correct. That means that the Warrior command will always have a name and a strength. The Battle command will always have two names. The Status command will not have any other information on it than just the word Status.

However, you will need to detect and report any issues indicating inconsistencies, such as:

<ul>

 <li>Noble command: if a Noble with a given name already exists.</li>

 <li>Warrior command:if a Warrior with a given name already exists.</li>

 <li>Hire command: If a Noble tries to hire a Warrior and either of them do not exist.</li>

 <li>Fire command: If a Noble tries to fire a Warrior and either the Noble does not exist or does not have the Warrior by that name in this army.</li>

 <li>Battle command: If a Noble initiates a battle with another Noble, but one or the other does not exist.</li>

</ul>

We have not specified the format of these error messages, so we’ll leave that up to you. (You get to be creative!)

Example input file (no errors):

Noble King_Arthur

Noble Lancelot_du_Lac

Noble Jim

Noble Linus_Torvalds

Noble Bill_Gates

Warrior Tarzan 10

Warrior Merlin 15

Warrior Conan 12

Warrior Spock 15

Warrior Xena 20

Warrior Hulk 8

Warrior Hercules 3

Hire Jim Spock

Hire Lancelot_du_Lac Conan

Hire King_Arthur Merlin

Hire Lancelot_du_Lac Hercules

Hire Linus_Torvalds Xena

Hire Bill_Gates Hulk

Hire King_Arthur Tarzan

Status

Fire King_Arthur Tarzan

Status

Battle King_Arthur Lancelot_du_Lac

Battle Jim Lancelot_du_Lac

Battle Linus_Torvalds Bill_Gates

Battle Bill_Gates Lancelot_du_Lac

Status

Clear

Status

<strong>Example output:</strong>

Status

======

Nobles:

King_Arthur has an army of 2

Merlin: 15

Tarzan: 10

Lancelot_du_Lac has an army of 2

Conan: 12

Hercules: 3

Jim has an army of 1

Spock: 15

Linus_Torvalds has an army of 1

Xena: 20

Bill_Gates has an army of 1

Hulk: 8

Unemployed Warriors:

NONE

You don’t work for me anymore Tarzan! — King_Arthur.

Status

======

Nobles:

King_Arthur has an army of 1

Merlin: 15

Lancelot_du_Lac has an army of 2

Conan: 12

Hercules: 3

Jim has an army of 1

Spock: 15

Linus_Torvalds has an army of 1

Xena: 20

Bill_Gates has an army of 1

Hulk: 8

Unemployed Warriors:

Tarzan: 10

King_Arthur battles Lancelot_du_Lac

Mutual Annihalation: King_Arthur and Lancelot_du_Lac die at each other’s hands

Jim battles Lancelot_du_Lac

He’s dead, Jim

Linus_Torvalds battles Bill_Gates

Linus_Torvalds defeats Bill_Gates

Bill_Gates battles Lancelot_du_Lac

Oh, NO!  They’re both dead!  Yuck!

Status

======

Nobles:

King_Arthur has an army of 1

Merlin: 0

Lancelot_du_Lac has an army of 2

Conan: 0

Hercules: 0

Jim has an army of 1

Spock: 15

Linus_Torvalds has an army of 1

Xena: 12

Bill_Gates has an army of 1

Hulk: 0

Unemployed Warriors:

Tarzan: 10

Status

======