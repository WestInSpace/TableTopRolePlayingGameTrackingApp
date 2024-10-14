TTRPG Tracker APP Documentation
by: Westin Mathies

Serial Number outline
* Number of Games (NumGames) (string)
	- Game (G###) (string)
		 = MyCharacter
			+ Character level (###.CL) (string)
			+ Strength level (###.STRL) (string)
			+ Strength mod (###.STRM) (string)
				> Strength saving throws (###.StST) (string)
				> Athletics (###.Athl) (string)
			+ Dextarity level (###.DEXL) (string)
			+ Dextarity mod (###.DEXM) (string)
				> Dextarity saving throws (###.DeST) (string)
				> Acrobatics (###.Acro) (string)
				> Sleight of hand (###.Slei) (string)
				> Stealth (###.Stea) (string)
			+ Constitution level (###.CONL) (string)
			+ Constitution mod (###.CONM) (string)
				> Constitution saving throws (###.CoST) (string)
			+ Intelligence level (###.INTL) (string)
			+ Intelligence mod (###.INTM) (string)
				> Intelligence saving throws (###.InST) (string)
				> Arcana (###.Arca) (string)
				> History (###.Hist) (string)
				> Investigation (###.Inve) (string)
				> Nature (###.Natu) (string)
				> Religion (###.Reli) (string)
			+ Wisdom level (###.WISL) (string)
			+ Wisdom mod (###.WISM) (string)
				> Wisdom saving throws (###.WiST) (string)
				> Animal handling (###.Anim) (string)
				> Insight (###.Insi) (string)
				> Medicine (###.Medi) (string)
				> Perception (###.Perc) (string)
				> Survival (###.Surv) (string)
			+ Charisma level (###.CHAL) (string)
			+ Charisma mod (###.CHAM) (string)
				> Charisma saving throws (###.ChST) (string)
				> Deception (###.Dece) (string)
				> Intimidation (###.Inti) (string)
				> Performance (###.Perf) (string)
				> Persuasion (###.Pers) (string)
			+ Name (###.Name) (string)
			+ Class (###.Clas) (string)
			+ Race (###.Race) (string)
			+ Background (###.Back) (string)
			+ Armor class (###.AC) (string)
			+ Temporary Health Points (###.THP) (string)
			+ Health Points (###.HP) (string)
			+ Inventory
				> Number of items (###.NI) (int)
Key: (GameNum.ItemNum.Letters)
				> Item1 (###.###.I) (string)
					~ Details1 (###.###.ID) (string)
				> Item2 (###.###.I) (string)
					~ Details2 (###.###.ID) (string)
				> Item3 (###.###.I) (string)
					~ Details3 (###.###.ID) (string)
				> . . .
					~ . . .
			+ Spells
				> Number of spells (###.NS) (int)
Key: (GameNum.SpellNum.Letters)
				> Spell1 (###.###.S) (string)
					~ details1 (###.###.SD) (string)
				> Spell2 (###.###.S) (string)
					~ details2 (###.###.SD) (string)
				> Spell3 (###.###.S) (string)
					~ details3 (###.###.SD) (string)
				> . . .
					~ . . .
		= NPCs
			+ Number of NPCs (###.NN) (int)
			+ NPC1 (###.N) (string)
				> details1 (###.ND) (string)
			+ NPC2 (###.N) (string)
				> details1 (###.ND) (string)
			+ NPC3 (###.N) (string)
				> details1 (###.ND) (string)

		= Locations
			+ Number of locations (###.NL) (int)
			+ location1 (###.L) (string)
				> details (###.LD) (string)
			+ location2 (###.L) (string)
				> details (###.LD) (string)
			+ location3 (###.L) (string)
				> details (###.LD) (string)
			+ . . .
				> . . .
		= Notes
			+ page1 (N.###) (string)
			+ page2 (N.###) (string)
			+ page3 (N.###) (string)
			+ . . .
ORDER:
    -
        =
            +
                >
                    ~
___________________________________________________________________________________________________________________________________________________________________________________________
TTRPG Tracker v0.0.0.U - Start
10/9/24
	I decided to change my development back to Unity becasue I decided that I already know that software well and
	I'm probably not going to publish this software anyway so Unity's new policies won't effect me. It will be
	just for the people I give it to to use. I may also publish it on my GitHub in order to add it to my
	portfolio. I also figured that Unity will make it eassier to build it on multiple platforms such as Windows,
	Android, Mac, and IOS.
	In this version you can create a new Game and name that game. So far that is all you can do. WHen the user
	clicks the add button the yare prompted to enter a name, when the yenter a name and click enter the name they
	entered is added to storage and the game template is copied, the name is chnaged on it, it is set as a child
	of the proper object, and the correct position is set.
	THe loadGame function also works by using the copyGame method and looping through the game name serial numbers
	based on the number of games that have been created. It gets the name of each of these games from storage and
	passes it to the copyGame method, the copy game methods then creates a copy of the game template . . . the
	same way it works for creating a new game.
___________________________________________________________________________________________________________________________________________________________________________________________
TTRPG Tracker v0.0.1.U - Skills
10/10/24
	I made a lot of progress in this version. I added three scenes and three scripts. Each scene has it's own
	scripts and values are passes between them by saving the value to PlayerPrefs then pulling that value from
	player prefs in the next scene. I know this was isn't very efficiant but I liked doing this way becsue this
	way I don't have to have a master object that isn't destroyed when switching scenes with a master script
	attatched. Doing it this way also gives a default value for whatever the last value was that was saved to
	PlayerPrefs.
	The first scene I added was the GameScreen, this is the scene that the user will see when they select a game
	to view. This scene is fairly simple and is used as a sort of "Train station" to transfer to other more
	complex and important scenes. In this scene there are four buttons, My Character, Locations, Notes, and NPCs.
	The only button I have worked on as of now is the My Character button, as this one is the most complex and
	many of the scripts and scenes written for this one can (and will be) used for the others. The next scene I
	created is called "MyCharacter" and this is the scene that the user sees when they choose to view their
	character after selecting a game. So far all that is in this scene are the six Skills that every character has
	 Strength, Dextarity, Constitution, Inteligence, Wisdom, and Charisma. Each of these tiles displays the level
	and modifier for each skill. Each tile is also a button and when the user clicks on it the "Skills" scene is
	loaded. This scene displays all of the abilities under that skill and allows the user to chnage the skill
	level, skill modifier, and the modifier of each ability. I decided to load in all the abilites by copying a
	template and chaning the details of that template (Very similar to how I make each Game in the MainScreen). I
	have an ArrayList for each skill that contains the name of all the abilities that that skills has under it
	(including the last part of the key for the saving throw) I then loop through the ArrayList according to what
	Skill the user selected and pass the names into a copy method that will copy the template and edit its name,
	positions and displayed information. The app is really startign to get some basic functionality.
___________________________________________________________________________________________________________________________________________________________________________________________
TTRPG Tracker v0.0.2.U - Inventory and MyChracter updates
10/11/24
	I decided to change it so that I pass the variable through a master script rather than reading and writing to
	storage to pass values between scenes and scripts. I decided this way would be more efficiant.
	For the record I know I spelled class with only one s for the name of the object and the variable name, I did
	this that way Name, Clas, Race, and Back all have four letters. (I also shortened background to Back) I did
	this for storage purposes when creating the serial numbers.
	In This version I made a lot of changes to thye MyCharacter scene aand script. MyCharacter now allows the
	user to input their Character Name, Class, Race, Background, AC, HP, Temp HP, as well as the charcter skills
	as before. The Inventory and Spell trackng now work as well. The Inventory and Spells use the same scene and
	script becsue the yfunction in the same way, the only thing that chnages is the "ItemType" variable whe none
	or the other button is pushed. This tells the script in the Items Scene to load spells or inventory Items.
	Each of the spell and inventory items also have detials that can be added when they are clicked on.
	A problem with the detials is that in order for them to save the user has to click the back button and go back
	to the Items scene. If they don't and they don't and they just close the app the details won't be saved. This
	is a bug that I probably won't be changing anytime soon becsue the alternitave as of now is to save it
	every time the user input a character (letter) and I think that would cause it to save way too often.
	I also made some changes to how values are updated. Before when the user chnaged a value the scene would be
	completely reloaded to display the updated value, now it will chnage the displaed text on just the one object
	instead of reloading the whole scene. This applied primarily to the Skills and MyCharacter script.
___________________________________________________________________________________________________________________________________________________________________________________________
TTRPG Tracker v0.0.3.U - Locations+NPCs
10/12/24
See a video of this version in action here: https://youtu.be/DSHGzGqZ8mU
	I got the NPCs and Locations buttons to work and the user can now create and save locations and NPCs along
	with detials for each. These two things use the same scripts and scenes as Inventory and Spells.
	Now everyting works except for Notes and the ability to delete Games, Items, Spells, NPCs, Locations, and
	NotePages. (Items, Spells, NPCs, and Locations will use the same methods)
	I also added Character Level to the MyCharacter Screen. THis did not requier much additinal code becsue it
	usses the same methods as Name, Class, Race, and Back. THe only code I had to add was a line for displaying
	the information on scene load. I also had to hadd a variable to stor the additional object.
	
	In the future I would like to add more info to my character such as Hit dice, and maybe more.
___________________________________________________________________________________________________________________________________________________________________________________________
TTRPG Tracker v0.0.4.U - 



