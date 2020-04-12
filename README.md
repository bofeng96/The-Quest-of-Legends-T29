# The-Quest-of-Legends

**GitHub**
https://github.com/CS591P1-29/The-Quest-of-Legends-T29  

**Compile and Run**  
When pwd --> XXXX/The-Quest-of-Legends-T29  
"javac Main.java"  
"java Main"  

**Gourp Member**  
Bofeng Liu
Nelson Mei

**Class Design:**  
Basically, lots of classes are exactly the same as the previous implementation of student Bofeng Liu(bofeng96). We just simply re-use them.
But our group add some new features and design new classes for Game "TheQuestOfLegends".


Interface:
 - DataInitialize (New feature: We read all data from files using text parsing. We merge the code from Bofeng and Nelson.)
 - Encounter
 - Fight (New feature: Ability augmentation at different type of cells)
 - Regeneration
 - BuyorSell (A new interface)

Cells (Base class)
   - PlainCells (Almost the same as CommonCells, but we color them)
   - InAccessibleCells (Almost the same as NonAccessibleCells, but we color them)
   - NexusCells/Markets (Nexus is a new class. Markets is the same as previous implementation)
   - BushCells (A new class)
   - KoulouCells (A new class)
   - CaveCells (A new class)

Roles (Base class)
   - Heroes
     - Warriors
     - Paladins
     - Sorcerers
   - Monsters
     - Dragons
     - Exoskeletons
     - Spirits

Items (Base class)
   - Weapons
   - Armors
   - Spells
     - IceSpells
     - FileSpells
     - LigntningSpells
   - Potions

Map (A new base class. The maps of two games have a bunch of common attributes, so we just re-use them)
   - TheQuestMap (It's the same as the previous implementation)
   - TheQuestOfLegendsMap (A new class that is slightly different from ↑)  

Teams (A new base class. The teams of two games have a bunch of common attributes, so we just re-use them)
   - TeamTheQuest (It's the same as the previous implementation)
   - TeamTheQuestOfLegends (A new class that is slightly different from ↑)  

Simulation (A new base class. The simulation process of two games have common attributes, so we just re-use them)
   - TheQuestSimulation (It's the same as the previous implementation)
   - TheQuestOfLegendsSimulation

Main (Add new functionality: player can choose which game he wants to play)  
Backpack (Every hero has a backpack which stores all his items)  
Probability  
Rounds (Add new functionality: Ability augmentation)  
ZshColors  

-----------------------------------------------
When hero is not in a fight with monster, he can
 - Display his status
 - Check his inventory
 - W/A/S/D
 - Teleport
 - B (back to Nexus cell)
 - Equip/Change Weapon
 - Equip/Change Armor
 - Display the map
 - Quit the game  
Only action "W/A/S/D", "Teleport" and "B" will cost one action point.

-----------------------------------------------
Assume that hero won't fight with monster when they encounter at a Nexus cell  

-----------------------------------------------
Pipeline for doing business:  
 - Do you want to do business?  
   - If yes, tell me who want to do business  
     - What kind of business? Buy or Sell?  
       - Buy what / Sell what  
After you buy a item, go back to the beginning. So you can choose if you want to do business again.  


-----------------------------------------------
In order to win a fight, you should:  
 - BUY a/some spells for each hero  
 - for each hero, BUY a weapon and EQUIP it   
 - for each hero, BUY a armor and EQUIP it  
If you don't do that, you will lose in most cases.  
If you encounter monsters before you arrive at a market, you definitely lose. The reality is really crucial. Restart a new game/life, don't hesitate.  


-----------------------------------------------
A fight consists of several rounds
At each round, each hero has only one action point. He can do one following action once.
 - Attack
 - Cast a spell
 - Drink a potion
 - Equip/Change Weapon
 - Equip/Change Armor
 - Display the status of your team(heroes) and monsters (I don't think this action deserves one action point because I display their status after attacking, casting or drinking without consuming action points.)

-----------------------------------------------
I adjusted the attributes of weapons. 
 - Set the base damage of Shield and Dagger to 300 and 400  
 - Then, base damage *= 5  
I changed some heroes' name.  
Heroes can't know monsters' status value before encountering them.  

