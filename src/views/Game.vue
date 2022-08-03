<template>
  <div style="height: 100vh">
    <div v-if="!isRedrawPhase" style="position: absolute; left: 20%; top: 1%; background-color: gray; width: 75vh; height: 20vh">
      <div @click="chosenCard=opponentBoard[0]" v-if="opponentHand[0].cardName && opponentHand[0].revealed" style="background-color: white; width: 15vh; height: 10vh; position: absolute; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentHand[0].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentHand[0].cardName }}</h1>
          <div v-if="opponentHand[0].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[0].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[0].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=opponentBoard[1]" v-if="opponentHand[1].cardName && opponentHand[1].revealed" style="background-color: white; width: 15vh; height: 10vh; position: absolute; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentHand[1].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentHand[1].cardName }}</h1>
          <div v-if="opponentHand[1].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[1].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[1].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=opponentBoard[2]" v-if="opponentHand[2].cardName && opponentHand[2].revealed" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 15vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentHand[2].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentHand[2].cardName }}</h1>
          <div v-if="opponentHand[2].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[2].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[2].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=opponentBoard[3]" v-if="opponentHand[3].cardName && opponentHand[3].revealed" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 15vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentHand[3].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentHand[3].cardName }}</h1>
          <div v-if="opponentHand[3].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[3].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[3].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=opponentBoard[4]" v-if="opponentHand[4].cardName && opponentHand[4].revealed" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 30vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentHand[4].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentHand[4].cardName }}</h1>
          <div v-if="opponentHand[4].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[4].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[4].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=opponentBoard[5]" v-if="opponentHand[5].cardName && opponentHand[5].revealed" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 30vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentHand[5].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentHand[5].cardName }}</h1>
          <div v-if="opponentHand[5].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[5].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[5].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=opponentBoard[6]" v-if="opponentHand[6].cardName && opponentHand[6].revealed" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 45vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentHand[6].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentHand[6].cardName }}</h1>
          <div v-if="opponentHand[6].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[6].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[6].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=opponentBoard[7]" v-if="opponentHand[7].cardName && opponentHand[7].revealed" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 45vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentHand[7].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentHand[7].cardName }}</h1>
          <div v-if="opponentHand[7].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[7].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[7].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=opponentBoard[8]" v-if="opponentHand[8].cardName && opponentHand[8].revealed" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 60vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentHand[8].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentHand[8].cardName }}</h1>
          <div v-if="opponentHand[8].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[8].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[8].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=opponentBoard[9]" v-if="opponentHand[9].cardName && opponentHand[9].revealed" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 60vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentHand[9].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentHand[9].cardName }}</h1>
          <div v-if="opponentHand[9].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[9].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentHand[9].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div >
        <div v-if="opponentHand[0].cardName && opponentHand[0].revealed==false" style="background-color: white; width: 15vh; height: 10vh; position: absolute; top: 0px;"><h1>???</h1></div>
        <div v-if="opponentHand[1].cardName && opponentHand[1].revealed==false" style="background-color: white; width: 15vh; height: 10vh; position: absolute; bottom: 0px"><h1>???</h1></div>
        <div v-if="opponentHand[2].cardName && opponentHand[2].revealed==false" style="background-color: white; width: 15vh; height: 10vh; position: absolute; top: 0px; left: 15vh"><h1>???</h1></div>
        <div v-if="opponentHand[3].cardName && opponentHand[3].revealed==false" style="background-color: white; width: 15vh; height: 10vh; position: absolute; bottom: 0px; left: 15vh"><h1>???</h1></div>
        <div v-if="opponentHand[4].cardName && opponentHand[4].revealed==false" style="background-color: white; width: 15vh; height: 10vh; position: absolute; top: 0px; left: 30vh"><h1>???</h1></div>
        <div v-if="opponentHand[5].cardName && opponentHand[5].revealed==false" style="background-color: white; width: 15vh; height: 10vh; position: absolute; bottom: 0px; left: 30vh"><h1>???</h1></div>
        <div v-if="opponentHand[6].cardName && opponentHand[6].revealed==false" style="background-color: white; width: 15vh; height: 10vh; position: absolute; top: 0px; left: 45vh"><h1>???</h1></div>
        <div v-if="opponentHand[7].cardName && opponentHand[7].revealed==false" style="background-color: white; width: 15vh; height: 10vh; position: absolute; bottom: 0px; left: 45vh"><h1>???</h1></div>
        <div v-if="opponentHand[8].cardName && opponentHand[8].revealed==false" style="background-color: white; width: 15vh; height: 10vh; position: absolute; top: 0px; left: 60vh"><h1>???</h1></div>
        <div v-if="opponentHand[9].cardName && opponentHand[9].revealed==false" style="background-color: white; width: 15vh; height: 10vh; position: absolute; bottom: 0px; left: 60vh"><h1>???</h1></div>
      </div>
      <div @click="chosenCardPlayedCard=null; showTutoredCard=true" v-if="chosenCardPlayedCard=='Revealed Card In Opponent Hand'">
          <div v-if="opponentHand[0].revealed" @click="chosenPlayableCard=opponentHand[0]" style="width: 15vh; height: 10vh; position: absolute; top: 0px;"></div>
          <div v-if="opponentHand[1].revealed" @click="chosenPlayableCard=opponentHand[1]" style="width: 15vh; height: 10vh; position: absolute; bottom: 0px;"></div>
          <div v-if="opponentHand[2].revealed" @click="chosenPlayableCard=opponentHand[2]" style="width: 15vh; height: 10vh; position: absolute; top: 0px; left: 15vh"></div>
          <div v-if="opponentHand[3].revealed" @click="chosenPlayableCard=opponentHand[3]" style="width: 15vh; height: 10vh; position: absolute; bottom: 0px; left: 15vh"></div>
          <div v-if="opponentHand[4].revealed" @click="chosenPlayableCard=opponentHand[4]" style="width: 15vh; height: 10vh; position: absolute; top: 0px; left: 30vh"></div>
          <div v-if="opponentHand[5].revealed" @click="chosenPlayableCard=opponentHand[5]" style="width: 15vh; height: 10vh; position: absolute; bottom: 0px; left: 30vh"></div>
          <div v-if="opponentHand[6].revealed" @click="chosenPlayableCard=opponentHand[6]" style="width: 15vh; height: 10vh; position: absolute; top: 0px; left: 45vh"></div>
          <div v-if="opponentHand[7].revealed" @click="chosenPlayableCard=opponentHand[7]" style="width: 15vh; height: 10vh; position: absolute; bottom: 0px; left: 45vh"></div>
          <div v-if="opponentHand[8].revealed" @click="chosenPlayableCard=opponentHand[8]" style="width: 15vh; height: 10vh; position: absolute; top: 0px; left: 60vh"></div>
          <div v-if="opponentHand[9].revealed" @click="chosenPlayableCard=opponentHand[9]" style="width: 15vh; height: 10vh; position: absolute; bottom: 0px; left: 60vh"></div>
      </div>
    </div> <!-- Opponent Hand --->
    <div v-if="opponentPassed && gameResult==''" style="position: absolute; left: 32%; top: 25%; font-size: 8vh;">Opponent has passed</div>
    <div style="position: absolute; top: 37%; left: 10%; height: 13vh; width: 80%;">
      <div @click="chosenCard=opponentBoard[0]" v-if="opponentBoard[0].cardName" style="width: 10%; height: 100%; position: absolute; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentBoard[0].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentBoard[0].cardName }}</h1>
          <div v-if="opponentBoard[0].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[0].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[0].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="opponentBoard[0].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left: 10%; color: #db2f04; font-size: 1.5vh" >{{ opponentBoard[0].statusses[0].duration }}</h1>
          <h1 v-if="opponentBoard[0].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left: 35%; color: #03d100; font-size: 1.5vh">{{ opponentBoard[0].statusses[1].duration }}</h1>
          <h1 v-if="opponentBoard[0].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left: 60%; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="opponentBoard[0].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left: 85%; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div @click="chosenCard=opponentBoard[1]" v-if="opponentBoard[1].cardName" style="width: 10%; height: 100%; position: absolute; left: 10%; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentBoard[1].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentBoard[1].cardName }}</h1>
          <div v-if="opponentBoard[1].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[1].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[1].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="opponentBoard[1].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left: 10%; color: #db2f04; font-size: 1.5vh" >{{ opponentBoard[1].statusses[0].duration }}</h1>
          <h1 v-if="opponentBoard[1].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left: 35%; color: #03d100; font-size: 1.5vh">{{ opponentBoard[1].statusses[1].duration }}</h1>
          <h1 v-if="opponentBoard[1].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left: 60%; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="opponentBoard[1].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left: 85%; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div @click="chosenCard=opponentBoard[2]" v-if="opponentBoard[2].cardName" style="width: 10%; height: 100%; position: absolute; left: 20%; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentBoard[2].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentBoard[2].cardName }}</h1>
          <div v-if="opponentBoard[2].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[2].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[2].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="opponentBoard[2].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left: 10%; color: #db2f04; font-size: 1.5vh" >{{ opponentBoard[2].statusses[0].duration }}</h1>
          <h1 v-if="opponentBoard[2].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left: 35%; color: #03d100; font-size: 1.5vh">{{ opponentBoard[2].statusses[1].duration }}</h1>
          <h1 v-if="opponentBoard[2].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left: 60%; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="opponentBoard[2].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left: 85%; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div @click="chosenCard=opponentBoard[3]" v-if="opponentBoard[3].cardName" style="width: 10%; height: 100%; position: absolute; left: 30%; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentBoard[3].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentBoard[3].cardName }}</h1>
          <div v-if="opponentBoard[3].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[3].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[3].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="opponentBoard[3].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left: 10%; color: #db2f04; font-size: 1.5vh" >{{ opponentBoard[3].statusses[0].duration }}</h1>
          <h1 v-if="opponentBoard[3].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left: 35%; color: #03d100; font-size: 1.5vh">{{ opponentBoard[3].statusses[1].duration }}</h1>
          <h1 v-if="opponentBoard[3].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left: 60%; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="opponentBoard[3].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left: 85%; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div @click="chosenCard=opponentBoard[4]" v-if="opponentBoard[4].cardName" style="width: 10%; height: 100%; position: absolute; left: 40%; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentBoard[4].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentBoard[4].cardName }}</h1>
          <div v-if="opponentBoard[4].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[4].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[4].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="opponentBoard[4].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left: 10%; color: #db2f04; font-size: 1.5vh" >{{ opponentBoard[4].statusses[0].duration }}</h1>
          <h1 v-if="opponentBoard[4].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left: 35%; color: #03d100; font-size: 1.5vh">{{ opponentBoard[4].statusses[1].duration }}</h1>
          <h1 v-if="opponentBoard[4].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left: 60%; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="opponentBoard[4].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left: 85%; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div @click="chosenCard=opponentBoard[5]" v-if="opponentBoard[5].cardName" style="width: 10%; height: 100%; position: absolute; left: 50%; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentBoard[5].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentBoard[5].cardName }}</h1>
          <div v-if="opponentBoard[5].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[5].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[5].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="opponentBoard[5].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left: 10%; color: #db2f04; font-size: 1.5vh" >{{ opponentBoard[5].statusses[0].duration }}</h1>
          <h1 v-if="opponentBoard[5].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left: 35%; color: #03d100; font-size: 1.5vh">{{ opponentBoard[5].statusses[1].duration }}</h1>
          <h1 v-if="opponentBoard[5].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left: 60%; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="opponentBoard[5].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left: 85%; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div @click="chosenCard=opponentBoard[6]" v-if="opponentBoard[6].cardName" style="width: 10%; height: 100%; position: absolute; left: 60%; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentBoard[6].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentBoard[6].cardName }}</h1>
          <div v-if="opponentBoard[6].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[6].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[6].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="opponentBoard[6].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left: 10%; color: #db2f04; font-size: 1.5vh" >{{ opponentBoard[6].statusses[0].duration }}</h1>
          <h1 v-if="opponentBoard[6].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left: 35%; color: #03d100; font-size: 1.5vh">{{ opponentBoard[6].statusses[1].duration }}</h1>
          <h1 v-if="opponentBoard[6].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left: 60%; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="opponentBoard[6].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left: 85%; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div @click="chosenCard=opponentBoard[7]" v-if="opponentBoard[7].cardName" style="width: 10%; height: 100%; position: absolute; left: 70%; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentBoard[7].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentBoard[7].cardName }}</h1>
          <div v-if="opponentBoard[7].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[7].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[7].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="opponentBoard[7].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left: 10%; color: #db2f04; font-size: 1.5vh" >{{ opponentBoard[7].statusses[0].duration }}</h1>
          <h1 v-if="opponentBoard[7].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left: 35%; color: #03d100; font-size: 1.5vh">{{ opponentBoard[7].statusses[1].duration }}</h1>
          <h1 v-if="opponentBoard[7].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left: 60%; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="opponentBoard[7].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left: 85%; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div @click="chosenCard=opponentBoard[8]" v-if="opponentBoard[8].cardName" style="width: 10%; height: 100%; position: absolute; left: 80%; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentBoard[8].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentBoard[8].cardName }}</h1>
          <div v-if="opponentBoard[8].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[8].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[8].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="opponentBoard[8].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left: 10%; color: #db2f04; font-size: 1.5vh" >{{ opponentBoard[8].statusses[0].duration }}</h1>
          <h1 v-if="opponentBoard[8].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left: 35%; color: #03d100; font-size: 1.5vh">{{ opponentBoard[8].statusses[1].duration }}</h1>
          <h1 v-if="opponentBoard[8].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left: 60%; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="opponentBoard[8].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left: 85%; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div @click="chosenCard=opponentBoard[9]" v-if="opponentBoard[9].cardName" style="width: 10%; height: 100%; position: absolute; left: 90%; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentBoard[9].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentBoard[9].cardName }}</h1>
          <div v-if="opponentBoard[9].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[9].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentBoard[9].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="opponentBoard[9].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left: 10%; color: #db2f04; font-size: 1.5vh" >{{ opponentBoard[9].statusses[0].duration }}</h1>
          <h1 v-if="opponentBoard[9].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left: 35%; color: #03d100; font-size: 1.5vh">{{ opponentBoard[9].statusses[1].duration }}</h1>
          <h1 v-if="opponentBoard[9].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left: 60%; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="opponentBoard[9].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left: 85%; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div v-if="chosenCardTargetType=='Enemy' && chosenCardTarget=='Manual' && opponentBoard[0].cardName" @click="processDeploy(0)" style="width: 10%; height: 100%; position: absolute;"></div>
      <div v-if="chosenCardTargetType=='Enemy' && chosenCardTarget=='Manual' && opponentBoard[1].cardName" @click="processDeploy(1)" style="width: 10%; height: 100%; left: 10%; position: absolute;"></div>
      <div v-if="chosenCardTargetType=='Enemy' && chosenCardTarget=='Manual' && opponentBoard[2].cardName" @click="processDeploy(2)" style="width: 10%; height: 100%; left: 20%; position: absolute;"></div>
      <div v-if="chosenCardTargetType=='Enemy' && chosenCardTarget=='Manual' && opponentBoard[3].cardName" @click="processDeploy(3)" style="width: 10%; height: 100%; left: 30%; position: absolute;"></div>
      <div v-if="chosenCardTargetType=='Enemy' && chosenCardTarget=='Manual' && opponentBoard[4].cardName" @click="processDeploy(4)" style="width: 10%; height: 100%; left: 40%; position: absolute;"></div>
      <div v-if="chosenCardTargetType=='Enemy' && chosenCardTarget=='Manual' && opponentBoard[5].cardName" @click="processDeploy(5)" style="width: 10%; height: 100%; left: 50%; position: absolute;"></div>
      <div v-if="chosenCardTargetType=='Enemy' && chosenCardTarget=='Manual' && opponentBoard[6].cardName" @click="processDeploy(6)" style="width: 10%; height: 100%; left: 60%; position: absolute;"></div>
      <div v-if="chosenCardTargetType=='Enemy' && chosenCardTarget=='Manual' && opponentBoard[7].cardName" @click="processDeploy(7)" style="width: 10%; height: 100%; left: 70%; position: absolute;"></div>
      <div v-if="chosenCardTargetType=='Enemy' && chosenCardTarget=='Manual' && opponentBoard[8].cardName" @click="processDeploy(8)" style="width: 10%; height: 100%; left: 80%; position: absolute;"></div>
      <div v-if="chosenCardTargetType=='Enemy' && chosenCardTarget=='Manual' && opponentBoard[9].cardName" @click="processDeploy(9)" style="width: 10%; height: 100%; left: 90%; position: absolute;"></div>
      <hr v-if="opponentBoard[0].cardName && opponentBoard[1].cardName" class="vertical" style="position: absolute; left: 9%; height: 100%">
      <hr v-if="opponentBoard[1].cardName && opponentBoard[2].cardName" class="vertical" style="position: absolute; left: 19%; height: 100%">
      <hr v-if="opponentBoard[2].cardName && opponentBoard[3].cardName" class="vertical" style="position: absolute; left: 29%; height: 100%">
      <hr v-if="opponentBoard[3].cardName && opponentBoard[4].cardName" class="vertical" style="position: absolute; left: 39%; height: 100%">
      <hr v-if="opponentBoard[4].cardName && opponentBoard[5].cardName" class="vertical" style="position: absolute; left: 49%; height: 100%">
      <hr v-if="opponentBoard[5].cardName && opponentBoard[6].cardName" class="vertical" style="position: absolute; left: 59%; height: 100%">
      <hr v-if="opponentBoard[6].cardName && opponentBoard[7].cardName" class="vertical" style="position: absolute; left: 69%; height: 100%">
      <hr v-if="opponentBoard[7].cardName && opponentBoard[8].cardName" class="vertical" style="position: absolute; left: 79%; height: 100%">
      <hr v-if="opponentBoard[8].cardName && opponentBoard[9].cardName" class="vertical" style="position: absolute; left: 89%; height: 100%">
    </div> <!-- Opponent Board --->
    <span v-if="opponentWon" class="circle" style="position: absolute; height: 6vh; width: 6vh; left: 2%; top: 24%; background-color: red"></span>
    <span v-if="opponentWonRound" class="circle" style="position: absolute; height: 6vh; width: 6vh; left: 2%; top: 32%; background-color: red;"></span>
    <div style="left: 15px; width: 11vh; height:10vh; border:3px solid #000; top: 41%; position: absolute"><h1 style="font-size: 9vh">{{ opponentScore }}</h1></div>
    <b-button v-if="showStartGame" @click="startGame()" variant="danger" style="position: absolute; top: 45%; left: 45%">Start Game</b-button>
    <div v-if="gameResult!=''" style="position: absolute; top: 40%; left: 30%; width: 40%; height: 20%; border: 5px solid black; padding: 5px; font-Size: 9vh; background-color: white; z-index: 2">{{ gameResult }}</div>
    <hr style="position: absolute; top: 49%; width: 99.5%; border: 3px solid">
    <div style="left: 15px; width: 11vh; height:10vh; border:3px solid #000; top: 51%; position: absolute"><h1 style="font-size: 9vh">{{ playerScore }}</h1></div>
    <span v-if="playerWonRound" class="circle" style="position: absolute; height: 6vh; width: 6vh; left: 2%; top: 64%; background-color: blue"></span>
    <span v-if="playerWon" class="circle" style="position: absolute; height: 6vh; width: 6vh; left: 2%; top: 72%; background-color: blue;"></span>
    <div v-if="isRedrawPhase" style="position: absolute; left: 20%; bottom: 36.5%; background-color: gray; width: 100vh; height: 26vh; z-index: 2">
      <div v-if="playerHand[0].cardName" style="background-color: white; width: 20vh; height: 13vh; position: absolute; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[0].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[0].cardName }}</h1>
          <div v-if="playerHand[0].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[0].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[0].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="playerHand[1].cardName" style="background-color: white; width: 20vh; height: 13vh; position: absolute; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[1].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[1].cardName }}</h1>
          <div v-if="playerHand[1].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[1].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[1].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="playerHand[2].cardName" style="background-color: white; width: 20vh; height: 13vh; position: absolute; left: 20vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[2].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[2].cardName }}</h1>
          <div v-if="playerHand[2].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[2].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[2].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="playerHand[3].cardName" style="background-color: white; width: 20vh; height: 13vh; position: absolute; left: 20vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[3].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[3].cardName }}</h1>
          <div v-if="playerHand[3].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[3].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[3].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="playerHand[4].cardName" style="background-color: white; width: 20vh; height: 13vh; position: absolute; left: 40vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[4].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[4].cardName }}</h1>
          <div v-if="playerHand[4].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[4].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[4].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="playerHand[5].cardName" style="background-color: white; width: 20vh; height: 13vh; position: absolute; left: 40vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[5].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[5].cardName }}</h1>
          <div v-if="playerHand[5].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[5].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[5].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="playerHand[6].cardName" style="background-color: white; width: 20vh; height: 13vh; position: absolute; left: 60vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[6].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[6].cardName }}</h1>
          <div v-if="playerHand[6].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[6].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[6].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="playerHand[7].cardName" style="background-color: white; width: 20vh; height: 13vh; position: absolute; left: 60vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[7].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[7].cardName }}</h1>
          <div v-if="playerHand[7].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[7].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[7].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="playerHand[8].cardName" style="background-color: white; width: 20vh; height: 13vh; position: absolute; left: 80vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[8].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[8].cardName }}</h1>
          <div v-if="playerHand[8].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[8].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[8].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="playerHand[9].cardName" style="background-color: white; width: 20vh; height: 13vh; position: absolute; left: 80vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[9].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[9].cardName }}</h1>
          <div v-if="playerHand[9].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[9].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[9].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <h1 style="position: absolute; bottom: 105%">Redraw phase: Click to inspect a card, double click to select a card to be replaced, double click again on that card to cancel selection. {{ 2-redrawnCards.length }} redraws left.</h1>
      <div v-if="redrawnCards.length<2">
        <div @click="chosenCard=playerHand[0]" @dblclick="redrawnCards.push(0)" v-if="playerHand[0].cardName && !redrawnCards.includes(0)" style="width: 20vh; height: 13vh; position: absolute; top: 0px"></div>
        <div @click="chosenCard=playerHand[1]" @dblclick="redrawnCards.push(1)" v-if="playerHand[1].cardName && !redrawnCards.includes(1)" style="width: 20vh; height: 13vh; position: absolute; bottom: 0px"></div>
        <div @click="chosenCard=playerHand[2]" @dblclick="redrawnCards.push(2)" v-if="playerHand[2].cardName && !redrawnCards.includes(2)" style="width: 20vh; height: 13vh; position: absolute; left: 20vh; top: 0px"></div>
        <div @click="chosenCard=playerHand[3]" @dblclick="redrawnCards.push(3)" v-if="playerHand[3].cardName && !redrawnCards.includes(3)" style="width: 20vh; height: 13vh; position: absolute; left: 20vh; bottom: 0px"></div>
        <div @click="chosenCard=playerHand[4]" @dblclick="redrawnCards.push(4)" v-if="playerHand[4].cardName && !redrawnCards.includes(4)" style="width: 20vh; height: 13vh; position: absolute; left: 40vh; top: 0px"></div>
        <div @click="chosenCard=playerHand[5]" @dblclick="redrawnCards.push(5)" v-if="playerHand[5].cardName && !redrawnCards.includes(5)" style="width: 20vh; height: 13vh; position: absolute; left: 40vh; bottom: 0px"></div>
        <div @click="chosenCard=playerHand[6]" @dblclick="redrawnCards.push(6)" v-if="playerHand[6].cardName && !redrawnCards.includes(6)" style="width: 20vh; height: 13vh; position: absolute; left: 60vh; top: 0px"></div>
        <div @click="chosenCard=playerHand[7]" @dblclick="redrawnCards.push(7)" v-if="playerHand[7].cardName && !redrawnCards.includes(7)" style="width: 20vh; height: 13vh; position: absolute; left: 60vh; bottom: 0px"></div>
        <div @click="chosenCard=playerHand[8]" @dblclick="redrawnCards.push(8)" v-if="playerHand[8].cardName && !redrawnCards.includes(8)" style="width: 20vh; height: 13vh; position: absolute; left: 80vh; top: 0px"></div>
        <div @click="chosenCard=playerHand[9]" @dblclick="redrawnCards.push(9)" v-if="playerHand[9].cardName && !redrawnCards.includes(9)" style="width: 20vh; height: 13vh; position: absolute; left: 80vh; bottom: 0px"></div>
      </div>
      <div>
        <div v-if="redrawnCards.includes(0)" @click="chosenCard=playerHand[0]" @dblclick="redrawnCards.splice(redrawnCards.indexOf(0), 1)" style="border-style: solid; border-color: red; border-width: 2px; width: 20vh; height: 13vh; position: absolute; top: 0px"></div>
        <div v-if="redrawnCards.includes(1)" @click="chosenCard=playerHand[1]" @dblclick="redrawnCards.splice(redrawnCards.indexOf(1), 1)" style="border-style: solid; border-color: red; border-width: 2px; width: 20vh; height: 13vh; position: absolute; bottom: 0px"></div>
        <div v-if="redrawnCards.includes(2)" @click="chosenCard=playerHand[2]" @dblclick="redrawnCards.splice(redrawnCards.indexOf(2), 1)" style="border-style: solid; border-color: red; border-width: 2px; width: 20vh; height: 13vh; position: absolute; left: 20vh; top: 0px"></div>
        <div v-if="redrawnCards.includes(3)" @click="chosenCard=playerHand[3]" @dblclick="redrawnCards.splice(redrawnCards.indexOf(3), 1)" style="border-style: solid; border-color: red; border-width: 2px; width: 20vh; height: 13vh; position: absolute; left: 20vh; bottom: 0px"></div>
        <div v-if="redrawnCards.includes(4)" @click="chosenCard=playerHand[4]" @dblclick="redrawnCards.splice(redrawnCards.indexOf(4), 1)" style="border-style: solid; border-color: red; border-width: 2px; width: 20vh; height: 13vh; position: absolute; left: 40vh; top: 0px"></div>
        <div v-if="redrawnCards.includes(5)" @click="chosenCard=playerHand[5]" @dblclick="redrawnCards.splice(redrawnCards.indexOf(5), 1)" style="border-style: solid; border-color: red; border-width: 2px; width: 20vh; height: 13vh; position: absolute; left: 40vh; bottom: 0px"></div>
        <div v-if="redrawnCards.includes(6)" @click="chosenCard=playerHand[6]" @dblclick="redrawnCards.splice(redrawnCards.indexOf(6), 1)" style="border-style: solid; border-color: red; border-width: 2px; width: 20vh; height: 13vh; position: absolute; left: 60vh; top: 0px"></div>
        <div v-if="redrawnCards.includes(7)" @click="chosenCard=playerHand[7]" @dblclick="redrawnCards.splice(redrawnCards.indexOf(7), 1)" style="border-style: solid; border-color: red; border-width: 2px; width: 20vh; height: 13vh; position: absolute; left: 60vh; bottom: 0px"></div>
        <div v-if="redrawnCards.includes(8)" @click="chosenCard=playerHand[8]" @dblclick="redrawnCards.splice(redrawnCards.indexOf(8), 1)" style="border-style: solid; border-color: red; border-width: 2px; width: 20vh; height: 13vh; position: absolute; left: 80vh; top: 0px"></div>
        <div v-if="redrawnCards.includes(9)" @click="chosenCard=playerHand[9]" @dblclick="redrawnCards.splice(redrawnCards.indexOf(9), 1)" style="border-style: solid; border-color: red; border-width: 2px; width: 20vh; height: 13vh; position: absolute; left: 80vh; bottom: 0px"></div>
      </div>
      <button style="font-size: 2vh; height: 5vh; background-color: antiquewhite; position: absolute; left: 105%; bottom: 50%" @click="confirmRedraw()">Confirm</button>
      <hr class="vertical" style="position: absolute; left: 19.3%; height: 26vh">
      <hr class="vertical" style="position: absolute; left: 39.3%; height: 26vh">
      <hr class="vertical" style="position: absolute; left: 59.3%; height: 26vh">
      <hr class="vertical" style="position: absolute; left: 79.3%; height: 26vh">
      <hr style="position: absolute; top: 45%; width: 100%; border: 1px solid">
    </div> <!-- Redraw Phase -->
    <div style="position: absolute; top: 51%; left: 10%; height: 13vh; width: 80%;">
      <div @click="chosenCard=playerBoard[0]" v-if="playerBoard[0].cardName" style="width: 10%; height: 100%; position: absolute; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerBoard[0].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerBoard[0].cardName }}</h1>
          <div v-if="playerBoard[0].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[0].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[0].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="playerBoard[0].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left 10%; color: #db2f04; font-size: 1.5vh" >{{ playerBoard[0].statusses[0].duration }}</h1>
          <h1 v-if="playerBoard[0].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left 35%; color: #03d100; font-size: 1.5vh">{{ playerBoard[0].statusses[1].duration }}</h1>
          <h1 v-if="playerBoard[0].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left 60%; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="playerBoard[0].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left 85%; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div @click="chosenCard=playerBoard[1]" v-if="playerBoard[1].cardName" style="width: 10%; height: 100%; position: absolute; left: 10%; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerBoard[1].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerBoard[1].cardName }}</h1>
          <div v-if="playerBoard[1].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[1].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[1].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="playerBoard[1].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left: 10%; color: #db2f04; font-size: 1.5vh" >{{ playerBoard[1].statusses[0].duration }}</h1>
          <h1 v-if="playerBoard[1].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left: 35%; color: #03d100; font-size: 1.5vh">{{ playerBoard[1].statusses[1].duration }}</h1>
          <h1 v-if="playerBoard[1].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left: 60%; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="playerBoard[1].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left: 85%; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div @click="chosenCard=playerBoard[2]" v-if="playerBoard[2].cardName" style="width: 10%; height: 100%; position: absolute; left: 20%; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerBoard[2].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerBoard[2].cardName }}</h1>
          <div v-if="playerBoard[2].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[2].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[2].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="playerBoard[2].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left: 10%; color: #db2f04; font-size: 1.5vh" >{{ playerBoard[2].statusses[0].duration }}</h1>
          <h1 v-if="playerBoard[2].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left: 35%; color: #03d100; font-size: 1.5vh">{{ playerBoard[2].statusses[1].duration }}</h1>
          <h1 v-if="playerBoard[2].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left: 60%; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="playerBoard[2].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left: 85%; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div @click="chosenCard=playerBoard[3]" v-if="playerBoard[3].cardName" style="width: 10%; height: 100%; position: absolute; left: 30%; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerBoard[3].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerBoard[3].cardName }}</h1>
          <div v-if="playerBoard[3].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[3].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[3].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="playerBoard[3].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left: 1vh; color: #db2f04; font-size: 1.5vh" >{{ playerBoard[3].statusses[0].duration }}</h1>
          <h1 v-if="playerBoard[3].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left: 3vh; color: #03d100; font-size: 1.5vh">{{ playerBoard[3].statusses[1].duration }}</h1>
          <h1 v-if="playerBoard[3].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left: 5vh; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="playerBoard[3].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left: 7vh; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div @click="chosenCard=playerBoard[4]" v-if="playerBoard[4].cardName" style="width: 10%; height: 100%; position: absolute; left: 40%; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerBoard[4].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerBoard[4].cardName }}</h1>
          <div v-if="playerBoard[4].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[4].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[4].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="playerBoard[4].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left: 10%; color: #db2f04; font-size: 1.5vh" >{{ playerBoard[4].statusses[0].duration }}</h1>
          <h1 v-if="playerBoard[4].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left: 35%; color: #03d100; font-size: 1.5vh">{{ playerBoard[4].statusses[1].duration }}</h1>
          <h1 v-if="playerBoard[4].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left: 60%; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="playerBoard[4].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left: 85%; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div @click="chosenCard=playerBoard[5]" v-if="playerBoard[5].cardName" style="width: 10%; height: 100%; position: absolute; left: 50%; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerBoard[5].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerBoard[5].cardName }}</h1>
          <div v-if="playerBoard[5].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[5].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[5].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="playerBoard[5].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left: 10%; color: #db2f04; font-size: 1.5vh" >{{ playerBoard[5].statusses[0].duration }}</h1>
          <h1 v-if="playerBoard[5].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left: 35%; color: #03d100; font-size: 1.5vh">{{ playerBoard[5].statusses[1].duration }}</h1>
          <h1 v-if="playerBoard[5].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left: 60%; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="playerBoard[5].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left: 85%; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div @click="chosenCard=playerBoard[6]" v-if="playerBoard[6].cardName" style="width: 10%; height: 100%; position: absolute; left: 60%; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerBoard[6].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerBoard[6].cardName }}</h1>
          <div v-if="playerBoard[6].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[6].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[6].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="playerBoard[6].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left: 10%; color: #db2f04; font-size: 1.5vh" >{{ playerBoard[6].statusses[0].duration }}</h1>
          <h1 v-if="playerBoard[6].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left: 35%; color: #03d100; font-size: 1.5vh">{{ playerBoard[6].statusses[1].duration }}</h1>
          <h1 v-if="playerBoard[6].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left: 60%; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="playerBoard[6].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left: 85%; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div @click="chosenCard=playerBoard[7]" v-if="playerBoard[7].cardName" style="width: 10%; height: 100%; position: absolute; left: 70%; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerBoard[7].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerBoard[7].cardName }}</h1>
          <div v-if="playerBoard[7].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[7].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[7].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="playerBoard[7].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left: 10%; color: #db2f04; font-size: 1.5vh" >{{ playerBoard[7].statusses[0].duration }}</h1>
          <h1 v-if="playerBoard[7].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left: 35%; color: #03d100; font-size: 1.5vh">{{ playerBoard[7].statusses[1].duration }}</h1>
          <h1 v-if="playerBoard[7].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left: 60%; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="playerBoard[7].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left: 85%; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div @click="chosenCard=playerBoard[8]" v-if="playerBoard[8].cardName" style="width: 10%; height: 100%; position: absolute; left: 80%; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerBoard[8].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerBoard[8].cardName }}</h1>
          <div v-if="playerBoard[8].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[8].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[8].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="playerBoard[8].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left: 10%; color: #db2f04; font-size: 1.5vh" >{{ playerBoard[8].statusses[0].duration }}</h1>
          <h1 v-if="playerBoard[8].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left: 35%; color: #03d100; font-size: 1.5vh">{{ playerBoard[8].statusses[1].duration }}</h1>
          <h1 v-if="playerBoard[8].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left: 60%; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="playerBoard[8].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left: 85%; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div @click="chosenCard=playerBoard[9]" v-if="playerBoard[9].cardName" style="width: 10%; height: 100%; position: absolute; left: 90%; background-color: white;">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerBoard[9].cardHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerBoard[9].cardName }}</h1>
          <div v-if="playerBoard[9].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[9].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerBoard[9].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
          <h1 v-if="playerBoard[9].statusses[0].status=='Bleeding'" style="position: absolute; bottom: 1vh; left: 10%; color: #db2f04; font-size: 1.5vh" >{{ playerBoard[9].statusses[0].duration }}</h1>
          <h1 v-if="playerBoard[9].statusses[1].status=='Vitality'" style="position: absolute; bottom: 1vh; left: 35%; color: #03d100; font-size: 1.5vh">{{ playerBoard[9].statusses[1].duration }}</h1>
          <h1 v-if="playerBoard[9].statusses[2].status=='Shield'" style="position: absolute; bottom: 1vh; left: 60%; color: #f5b916; font-size: 1.5vh">S</h1>
          <h1 v-if="playerBoard[9].statusses[3].status=='Freeze'" style="position: absolute; bottom: 1vh; left: 85%; color: #1cebe7; font-size: 1.5vh">F</h1>
      </div>
      <div v-if="chosenPlayableCard.cardName && !isRedrawPhase">
        <div v-if="playerBoard[0].cardName==null" @click="playCard(0)" style="width: 9%; height: 100%; position: absolute; background-color: #80ffff"></div>
        <div v-if="playerBoard[1].cardName==null" @click="playCard(1)" style="width: 9%; height: 100%; left: 10%; position: absolute; background-color: #80ffff"></div>
        <div v-if="playerBoard[2].cardName==null" @click="playCard(2)" style="width: 9%; height: 100%; left: 20%; position: absolute; background-color: #80ffff"></div>
        <div v-if="playerBoard[3].cardName==null" @click="playCard(3)" style="width: 9%; height: 100%; left: 30%; position: absolute; background-color: #80ffff"></div>
        <div v-if="playerBoard[4].cardName==null" @click="playCard(4)" style="width: 9%; height: 100%; left: 40%; position: absolute; background-color: #80ffff"></div>
        <div v-if="playerBoard[5].cardName==null" @click="playCard(5)" style="width: 9%; height: 100%; left: 50%; position: absolute; background-color: #80ffff"></div>
        <div v-if="playerBoard[6].cardName==null" @click="playCard(6)" style="width: 9%; height: 100%; left: 60%; position: absolute; background-color: #80ffff"></div>
        <div v-if="playerBoard[7].cardName==null" @click="playCard(7)" style="width: 9%; height: 100%; left: 70%; position: absolute; background-color: #80ffff"></div>
        <div v-if="playerBoard[8].cardName==null" @click="playCard(8)" style="width: 9%; height: 100%; left: 80%; position: absolute; background-color: #80ffff"></div>
        <div v-if="playerBoard[9].cardName==null" @click="playCard(9)" style="width: 9%; height: 100%; left: 90%; position: absolute; background-color: #80ffff"></div>
      </div>
      <div v-if="chosenCardTargetType=='Ally' && chosenCardTarget=='Manual'">
        <div v-if="playerBoard[0].cardName" @click="processDeploy(0)" style="width: 10%; height: 100%; position: absolute;"></div>
        <div v-if="playerBoard[1].cardName" @click="processDeploy(1)" style="width: 10%; height: 100%; left: 10%; position: absolute;"></div>
        <div v-if="playerBoard[2].cardName" @click="processDeploy(2)" style="width: 10%; height: 100%; left: 20%; position: absolute;"></div>
        <div v-if="playerBoard[3].cardName" @click="processDeploy(3)" style="width: 10%; height: 100%; left: 30%; position: absolute;"></div>
        <div v-if="playerBoard[4].cardName" @click="processDeploy(4)" style="width: 10%; height: 100%; left: 40%; position: absolute;"></div>
        <div v-if="playerBoard[5].cardName" @click="processDeploy(5)" style="width: 10%; height: 100%; left: 50%; position: absolute;"></div>
        <div v-if="playerBoard[6].cardName" @click="processDeploy(6)" style="width: 10%; height: 100%; left: 60%; position: absolute;"></div>
        <div v-if="playerBoard[7].cardName" @click="processDeploy(7)" style="width: 10%; height: 100%; left: 70%; position: absolute;"></div>
        <div v-if="playerBoard[8].cardName" @click="processDeploy(8)" style="width: 10%; height: 100%; left: 80%; position: absolute;"></div>
        <div v-if="playerBoard[9].cardName" @click="processDeploy(9)" style="width: 10%; height: 100%; left: 90%; position: absolute;"></div>
      </div>
      <hr v-if="playerBoard[0].cardName && playerBoard[1].cardName" class="vertical" style="position: absolute; left: 9%; height: 100%">
      <hr v-if="playerBoard[1].cardName && playerBoard[2].cardName" class="vertical" style="position: absolute; left: 19%; height: 100%">
      <hr v-if="playerBoard[2].cardName && playerBoard[3].cardName" class="vertical" style="position: absolute; left: 29%; height: 100%">
      <hr v-if="playerBoard[3].cardName && playerBoard[4].cardName" class="vertical" style="position: absolute; left: 39%; height: 100%">
      <hr v-if="playerBoard[4].cardName && playerBoard[5].cardName" class="vertical" style="position: absolute; left: 49%; height: 100%">
      <hr v-if="playerBoard[5].cardName && playerBoard[6].cardName" class="vertical" style="position: absolute; left: 59%; height: 100%">
      <hr v-if="playerBoard[6].cardName && playerBoard[7].cardName" class="vertical" style="position: absolute; left: 69%; height: 100%">
      <hr v-if="playerBoard[7].cardName && playerBoard[8].cardName" class="vertical" style="position: absolute; left: 79%; height: 100%">
      <hr v-if="playerBoard[8].cardName && playerBoard[9].cardName" class="vertical" style="position: absolute; left: 89%; height: 100%">
    </div> <!-- Player Board --->
    <div v-if="playerPassed && gameResult=='' && !isRedrawPhase" style="position: absolute; left: 32%; bottom: 25%; font-size: 8vh;">You have passed</div>
    <div v-if="!isRedrawPhase" style="position: absolute; left: 20%; bottom: 1%; background-color: gray; width: 75vh; height: 20vh">
      <div v-if="playerHand[0].cardName" style="background-color: white; width: 15vh; height: 10vh; position: absolute; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[0].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[0].cardName }}</h1>
          <div v-if="playerHand[0].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[0].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[0].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="playerHand[1].cardName" style="background-color: white; width: 15vh; height: 10vh; position: absolute; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[1].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[1].cardName }}</h1>
          <div v-if="playerHand[1].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[1].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[1].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="playerHand[2].cardName" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 15vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[2].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[2].cardName }}</h1>
          <div v-if="playerHand[2].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[2].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[2].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="playerHand[3].cardName" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 15vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[3].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[3].cardName }}</h1>
          <div v-if="playerHand[3].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[3].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[3].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="playerHand[4].cardName" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 30vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[4].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[4].cardName }}</h1>
          <div v-if="playerHand[4].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[4].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[4].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="playerHand[5].cardName" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 30vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[5].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[5].cardName }}</h1>
          <div v-if="playerHand[5].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[5].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[5].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="playerHand[6].cardName" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 45vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[6].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[6].cardName }}</h1>
          <div v-if="playerHand[6].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[6].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[6].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="playerHand[7].cardName" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 45vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[7].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[7].cardName }}</h1>
          <div v-if="playerHand[7].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[7].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[7].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="playerHand[8].cardName" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 60vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[8].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[8].cardName }}</h1>
          <div v-if="playerHand[8].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[8].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[8].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="playerHand[9].cardName" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 60vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerHand[9].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerHand[9].cardName }}</h1>
          <div v-if="playerHand[9].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[9].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerHand[9].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="chosenCardPlayedCard!='Any Card From Own Deck' && !isEnemyTurn && !showTutoredCard && chosenCardTarget!='Manual' && !playerPlayed && !playerPassed">
        <div @click="chosenCard=playerHand[0]; chosenPlayableCard=playerHand[0]; chosenPlayableCardIndex=0" v-if="playerHand[0].cardName" style="width: 15vh; height: 10vh; position: absolute; top: 0px"></div>
        <div @click="chosenCard=playerHand[1]; chosenPlayableCard=playerHand[1]; chosenPlayableCardIndex=1" v-if="playerHand[1].cardName" style="width: 15vh; height: 10vh; position: absolute; bottom: 0px"></div>
        <div @click="chosenCard=playerHand[2]; chosenPlayableCard=playerHand[2]; chosenPlayableCardIndex=2" v-if="playerHand[2].cardName" style="width: 15vh; height: 10vh; position: absolute; left: 15vh; top: 0px"></div>
        <div @click="chosenCard=playerHand[3]; chosenPlayableCard=playerHand[3]; chosenPlayableCardIndex=3" v-if="playerHand[3].cardName" style="width: 15vh; height: 10vh; position: absolute; left: 15vh; bottom: 0px"></div>
        <div @click="chosenCard=playerHand[4]; chosenPlayableCard=playerHand[4]; chosenPlayableCardIndex=4" v-if="playerHand[4].cardName" style="width: 15vh; height: 10vh; position: absolute; left: 30vh; top: 0px"></div>
        <div @click="chosenCard=playerHand[5]; chosenPlayableCard=playerHand[5]; chosenPlayableCardIndex=5" v-if="playerHand[5].cardName" style="width: 15vh; height: 10vh; position: absolute; left: 30vh; bottom: 0px"></div>
        <div @click="chosenCard=playerHand[6]; chosenPlayableCard=playerHand[6]; chosenPlayableCardIndex=6" v-if="playerHand[6].cardName" style="width: 15vh; height: 10vh; position: absolute; left: 45vh; top: 0px"></div>
        <div @click="chosenCard=playerHand[7]; chosenPlayableCard=playerHand[7]; chosenPlayableCardIndex=7" v-if="playerHand[7].cardName" style="width: 15vh; height: 10vh; position: absolute; left: 45vh; bottom: 0px"></div>
        <div @click="chosenCard=playerHand[8]; chosenPlayableCard=playerHand[8]; chosenPlayableCardIndex=8" v-if="playerHand[8].cardName" style="width: 15vh; height: 10vh; position: absolute; left: 60vh; top: 0px"></div>
        <div @click="chosenCard=playerHand[9]; chosenPlayableCard=playerHand[9]; chosenPlayableCardIndex=9" v-if="playerHand[9].cardName" style="width: 15vh; height: 10vh; position: absolute; left: 60vh; bottom: 0px"></div>
      </div>
      <hr class="vertical" style="position: absolute; left: 19%; height: 20vh">
      <hr class="vertical" style="position: absolute; left: 39%; height: 20vh">
      <hr class="vertical" style="position: absolute; left: 59%; height: 20vh">
      <hr class="vertical" style="position: absolute; left: 79%; height: 20vh">
      <hr style="position: absolute; top: 44%; width: 100%; border: 1px solid">
    </div> <!-- Player Hand --->
    <div v-if="showDeck" style="position: absolute; left: 60%; top: 12%; background-color: gray; width: 75vh; height: 20vh">
      <div @click="chosenCard=visibleDeck[0]" v-if="visibleDeck[0]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ visibleDeck[0].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ visibleDeck[0].cardName }}</h1>
          <div v-if="visibleDeck[0].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[0].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[0].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=visibleDeck[1]" v-if="visibleDeck[1]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ visibleDeck[1].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ visibleDeck[1].cardName }}</h1>
          <div v-if="visibleDeck[1].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[1].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[1].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=visibleDeck[2]" v-if="visibleDeck[2]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 15vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ visibleDeck[2].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ visibleDeck[2].cardName }}</h1>
          <div v-if="visibleDeck[2].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[2].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[2].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=visibleDeck[3]" v-if="visibleDeck[3]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 15vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ visibleDeck[3].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ visibleDeck[3].cardName }}</h1>
          <div v-if="visibleDeck[3].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[3].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[3].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=visibleDeck[4]" v-if="visibleDeck[4]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 30vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ visibleDeck[4].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ visibleDeck[4].cardName }}</h1>
          <div v-if="visibleDeck[4].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[4].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[4].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=visibleDeck[5]" v-if="visibleDeck[5]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 30vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ visibleDeck[5].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ visibleDeck[5].cardName }}</h1>
          <div v-if="visibleDeck[5].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[5].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[5].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=visibleDeck[6]" v-if="visibleDeck[6]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 45vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ visibleDeck[6].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ visibleDeck[6].cardName }}</h1>
          <div v-if="visibleDeck[6].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[6].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[6].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=visibleDeck[7]" v-if="visibleDeck[7]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 45vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ visibleDeck[7].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ visibleDeck[7].cardName }}</h1>
          <div v-if="visibleDeck[7].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[7].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[7].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=visibleDeck[8]" v-if="visibleDeck[8]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 60vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ visibleDeck[8].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ visibleDeck[8].cardName }}</h1>
          <div v-if="visibleDeck[8].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[8].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[8].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=visibleDeck[9]" v-if="visibleDeck[9]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 60vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ visibleDeck[9].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ visibleDeck[9].cardName }}</h1>
          <div v-if="visibleDeck[9].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[9].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="visibleDeck[9].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCardPlayedCard=null; showDeck=false; showTutoredCard=true" v-if="chosenCardPlayedCard=='Any Card From Own Deck'">
          <div @click="chosenPlayableCard=visibleDeck[0]; visibleDeck.splice(0, 1)" v-if="visibleDeck[0]" style="width: 15vh; height: 10vh; position: absolute; top: 0px"></div>
          <div @click="chosenPlayableCard=visibleDeck[1]; visibleDeck.splice(1, 1)" v-if="visibleDeck[1]" style="width: 15vh; height: 10vh; position: absolute; bottom: 0px"></div>
          <div @click="chosenPlayableCard=visibleDeck[2]; visibleDeck.splice(2, 1)" v-if="visibleDeck[2]" style="width: 15vh; height: 10vh; position: absolute; left: 15vh; top: 0px"></div>
          <div @click="chosenPlayableCard=visibleDeck[3]; visibleDeck.splice(3, 1)" v-if="visibleDeck[3]" style="width: 15vh; height: 10vh; position: absolute; left: 15vh; bottom: 0px"></div>
          <div @click="chosenPlayableCard=visibleDeck[4]; visibleDeck.splice(4, 1)" v-if="visibleDeck[4]" style="width: 15vh; height: 10vh; position: absolute; left: 30vh; top: 0px"></div>
          <div @click="chosenPlayableCard=visibleDeck[5]; visibleDeck.splice(5, 1)" v-if="visibleDeck[5]" style="width: 15vh; height: 10vh; position: absolute; left: 30vh; bottom: 0px"></div>
          <div @click="chosenPlayableCard=visibleDeck[6]; visibleDeck.splice(6, 1)" v-if="visibleDeck[6]" style="width: 15vh; height: 10vh; position: absolute; left: 45vh; top: 0px"></div>
          <div @click="chosenPlayableCard=visibleDeck[7]; visibleDeck.splice(7, 1)" v-if="visibleDeck[7]" style="width: 15vh; height: 10vh; position: absolute; left: 45vh; bottom: 0px"></div>
          <div @click="chosenPlayableCard=visibleDeck[8]; visibleDeck.splice(8, 1)" v-if="visibleDeck[8]" style="width: 15vh; height: 10vh; position: absolute; left: 60vh; top: 0px"></div>
          <div @click="chosenPlayableCard=visibleDeck[9]; visibleDeck.splice(9, 1)" v-if="visibleDeck[9]" style="width: 15vh; height: 10vh; position: absolute; left: 60vh; bottom: 0px"></div>
      </div>
      <hr class="vertical" style="position: absolute; left: 18%; height: 20vh">
      <hr class="vertical" style="position: absolute; left: 38%; height: 20vh">
      <hr class="vertical" style="position: absolute; left: 58%; height: 20vh">
      <hr class="vertical" style="position: absolute; left: 78%; height: 20vh">
      <hr style="position: absolute; top: 40%; width: 99.5%; border: 1px solid">
    </div> <!-- Player Deck  --->
    <div v-if="showPlayerGraveyard" style="position: absolute; left: 60%; top: 12%; background-color: gray; width: 75vh; height: 20vh">
      <div @click="chosenCard=playerGraveyard[0]" v-if="playerGraveyard[0]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerGraveyard[0].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerGraveyard[0].cardName }}</h1>
          <div v-if="playerGraveyard[0].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[0].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[0].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=playerGraveyard[1]" v-if="playerGraveyard[1]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerGraveyard[1].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerGraveyard[1].cardName }}</h1>
          <div v-if="playerGraveyard[1].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[1].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[1].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=playerGraveyard[2]" v-if="playerGraveyard[2]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 15vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerGraveyard[2].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerGraveyard[2].cardName }}</h1>
          <div v-if="playerGraveyard[2].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[2].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[2].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=playerGraveyard[3]" v-if="playerGraveyard[3]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 15vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerGraveyard[3].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerGraveyard[3].cardName }}</h1>
          <div v-if="playerGraveyard[3].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[3].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[3].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=playerGraveyard[4]" v-if="playerGraveyard[4]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 30vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerGraveyard[4].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerGraveyard[4].cardName }}</h1>
          <div v-if="playerGraveyard[4].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[4].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[4].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=playerGraveyard[5]" v-if="playerGraveyard[5]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 30vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerGraveyard[5].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerGraveyard[5].cardName }}</h1>
          <div v-if="playerGraveyard[5].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[5].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[5].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=playerGraveyard[6]" v-if="playerGraveyard[6]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 45vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerGraveyard[6].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerGraveyard[6].cardName }}</h1>
          <div v-if="playerGraveyard[6].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[6].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[6].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=playerGraveyard[7]" v-if="playerGraveyard[7]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 45vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerGraveyard[7].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerGraveyard[7].cardName }}</h1>
          <div v-if="playerGraveyard[7].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[7].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[7].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=playerGraveyard[8]" v-if="playerGraveyard[8]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 60vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerGraveyard[8].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerGraveyard[8].cardName }}</h1>
          <div v-if="playerGraveyard[8].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[8].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[8].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=playerGraveyard[9]" v-if="playerGraveyard[9]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 60vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ playerGraveyard[9].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ playerGraveyard[9].cardName }}</h1>
          <div v-if="playerGraveyard[9].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[9].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="playerGraveyard[9].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div v-if="chosenCardEffect=='Grave Consume' || chosenCardEffect=='Copy Grave Unit'">
        <div v-if="playerGraveyard[0]" @click="processDeploy(0)" style="width: 15vh; height: 10vh; position: absolute; top: 0px"></div>
        <div v-if="playerGraveyard[1]" @click="processDeploy(1)" style="width: 15vh; height: 10vh; position: absolute; bottom: 0px"></div>
        <div v-if="playerGraveyard[2]" @click="processDeploy(2)" style="width: 15vh; height: 10vh; position: absolute; left: 15vh; top: 0px"></div>
        <div v-if="playerGraveyard[3]" @click="processDeploy(3)" style="width: 15vh; height: 10vh; position: absolute; left: 15vh; bottom: 0px"></div>
        <div v-if="playerGraveyard[4]" @click="processDeploy(4)" style="width: 15vh; height: 10vh; position: absolute; left: 30vh; top: 0px"></div>
        <div v-if="playerGraveyard[5]" @click="processDeploy(5)" style="width: 15vh; height: 10vh; position: absolute; left: 30vh; bottom: 0px"></div>
        <div v-if="playerGraveyard[6]" @click="processDeploy(6)" style="width: 15vh; height: 10vh; position: absolute; left: 45vh; top: 0px"></div>
        <div v-if="playerGraveyard[7]" @click="processDeploy(7)" style="width: 15vh; height: 10vh; position: absolute; left: 45vh; bottom: 0px"></div>
        <div v-if="playerGraveyard[8]" @click="processDeploy(8)" style="width: 15vh; height: 10vh; position: absolute; left: 60vh; top: 0px"></div>
        <div v-if="playerGraveyard[9]" @click="processDeploy(9)" style="width: 15vh; height: 10vh; position: absolute; left: 60vh; bottom: 0px"></div>
      </div>
      <hr class="vertical" style="position: absolute; left: 18%; height: 20vh">
      <hr class="vertical" style="position: absolute; left: 38%; height: 20vh">
      <hr class="vertical" style="position: absolute; left: 58%; height: 20vh">
      <hr class="vertical" style="position: absolute; left: 78%; height: 20vh">
      <hr style="position: absolute; top: 40%; width: 99.5%; border: 1px solid">
    </div> <!-- Player Graveyard  --->
    <div v-if="showOpponentGraveyard" style="position: absolute; left: 60%; top: 12%; background-color: gray; width: 75vh; height: 20vh">
      <div @click="chosenCard=opponentGraveyard[0]" v-if="opponentGraveyard[0]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentGraveyard[0].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentGraveyard[0].cardName }}</h1>
          <div v-if="opponentGraveyard[0].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[0].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[0].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=opponentGraveyard[1]" v-if="opponentGraveyard[1]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentGraveyard[1].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentGraveyard[1].cardName }}</h1>
          <div v-if="opponentGraveyard[1].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[1].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[1].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=opponentGraveyard[2]" v-if="opponentGraveyard[2]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 15vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentGraveyard[2].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentGraveyard[2].cardName }}</h1>
          <div v-if="opponentGraveyard[2].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[2].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[2].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=opponentGraveyard[3]" v-if="opponentGraveyard[3]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 15vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentGraveyard[3].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentGraveyard[3].cardName }}</h1>
          <div v-if="opponentGraveyard[3].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[3].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[3].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=opponentGraveyard[4]" v-if="opponentGraveyard[4]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 30vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentGraveyard[4].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentGraveyard[4].cardName }}</h1>
          <div v-if="opponentGraveyard[4].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[4].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[4].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=opponentGraveyard[5]" v-if="opponentGraveyard[5]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 30vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentGraveyard[5].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentGraveyard[5].cardName }}</h1>
          <div v-if="opponentGraveyard[5].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[5].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[5].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=opponentGraveyard[6]" v-if="opponentGraveyard[6]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 45vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentGraveyard[6].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentGraveyard[6].cardName }}</h1>
          <div v-if="opponentGraveyard[6].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[6].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[6].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=opponentGraveyard[7]" v-if="opponentGraveyard[7]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 45vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentGraveyard[7].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentGraveyard[7].cardName }}</h1>
          <div v-if="opponentGraveyard[7].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[7].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[7].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=opponentGraveyard[8]" v-if="opponentGraveyard[8]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 60vh; top: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentGraveyard[8].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentGraveyard[8].cardName }}</h1>
          <div v-if="opponentGraveyard[8].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[8].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[8].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <div @click="chosenCard=opponentGraveyard[9]" v-if="opponentGraveyard[9]" style="background-color: white; width: 15vh; height: 10vh; position: absolute; left: 60vh; bottom: 0px">
          <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ opponentGraveyard[9].cardBaseHealth }}</div></span>
          <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ opponentGraveyard[9].cardName }}</h1>
          <div v-if="opponentGraveyard[9].cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[9].cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
          <div v-if="opponentGraveyard[9].cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
      </div>
      <hr class="vertical" style="position: absolute; left: 18%; height: 20vh">
      <hr class="vertical" style="position: absolute; left: 38%; height: 20vh">
      <hr class="vertical" style="position: absolute; left: 58%; height: 20vh">
      <hr class="vertical" style="position: absolute; left: 78%; height: 20vh">
      <hr style="position: absolute; top: 40%; width: 99.5%; border: 1px solid">
    </div> <!-- Opponent Graveyard  --->
    <b-button v-if="(showDeck || showPlayerGraveyard || showOpponentGraveyard) && chosenCardPlayedCard!='Any Card From Own Deck'" @click="showDeck=false; showPlayerGraveyard=false; showOpponentGraveyard=false" style="position: absolute; left: 93%; top: 32%;">close</b-button>
    <div @click="showDeck=true; showPlayerGraveyard=false; showOpponentGraveyard=false" style="position: absolute; left: 70%; bottom: 1%; background-color: gray; width: 15vh; height: 8vh">
        <h1>{{ playerDeck.length }}</h1>
    </div>
    <div v-if="chosenCardTarget=='Manual'" style="position: absolute; left: 2%; bottom: 20%;">
      <h1 v-if="chosenCardTargetType=='Ally' && playerBoard.length>1">Choose an allied unit</h1>
      <h1 v-if="chosenCardTargetType=='Enemy' && opponentBoard.length>1 && chosenCardEffect!='Removal'">Choose an enemy unit</h1>
      <h1 v-if="chosenCardEffect=='Copy Grave Unit' || chosenCardEffect=='Grave Consume'">Choose an allied unit from the graveyard</h1>
      <h1 v-if="chosenCardEffect=='Removal' && chosenCardRemovalCondition=='Above Value'">Choose an enemy unit above {{ chosenCardRemovalConditionValue }} health</h1>
      <h1 v-if="chosenCardEffect=='Removal' && chosenCardRemovalCondition=='Is Bleeding'">Choose a bleeding enemy unit</h1>
      <h1 v-if="chosenCardTargetType=='Opponent Hand'">Choose a revealed card from the opponent's hand</h1>
    </div> <!-- Guiding text --->
    <div v-if="showTutoredCard" @click="chosenCard=chosenPlayableCard" style="position: absolute; left: 70%; top: 30%; background-color: white; width: 30vh; height: 15vh">
        <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center"><div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ chosenPlayableCard.cardBaseHealth }}</div></span>
        <h1 style="position: absolute; top: 4vh; left: 2vh; font-size: 2vh">{{ chosenPlayableCard.cardName }}</h1>
        <div v-if="chosenPlayableCard.cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
        <div v-if="chosenPlayableCard.cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
        <div v-if="chosenPlayableCard.cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
    </div> <!-- Tutored Card --->
    <div style="position: absolute; left: 70%; top: 1%; background-color: gray; width: 15vh; height: 8vh">
        <h1>{{ opponentDeck.length }}</h1>
    </div>
    <div @click="showDeck=false; showPlayerGraveyard=true; showOpponentGraveyard=false" style="position: absolute; left: 5%; bottom: 1%; background-color: gray; width: 15vh; height: 8vh">
        <h1>{{ playerGraveyard.length }}</h1>
    </div>
    <div v-if="chosenPlayableCard.cardName" @click="discardCard()" style="position: absolute; left: 5%; bottom: 1%; background-color: red; width: 15vh; height: 8vh">
        <h1>{{ playerGraveyard.length }}</h1>
    </div>
    <div @click="showDeck=false; showPlayerGraveyard=false; showOpponentGraveyard=true" style="position: absolute; left: 5%; top: 1%; background-color: gray; width: 15vh; height: 8vh">
        <h1>{{ opponentGraveyard.length }}</h1>
    </div>
    <div v-if="chosenCard.cardName" style="position: absolute; right: 2%; bottom: 10%; background-color: white; width: 45vh; height: 25vh">
        <span class="circle" style="position: absolute; left: 5px; top: 5px; text-align: center">
        <div style="position: absolute; top: 5px; left: 10px; font-size: 1.75vh">{{ chosenCard.cardBaseHealth }}</div></span>
        <h1 style="position: absolute; top: 5vh; left: 3vh; font-size: 2vh">{{ chosenCard.cardName }}</h1>
        <div v-if="chosenCard.cardRarity=='Bronze'" style="position: absolute; background-color: #cc6600; width: 2vh; height: 2vh; right: 10px"></div>
        <div v-if="chosenCard.cardRarity=='Silver'" style="position: absolute; background-color: #a6a6a6; width: 2vh; height: 2vh; right: 10px"></div>
        <div v-if="chosenCard.cardRarity=='Gold'" style="position: absolute; background-color: #e6b800; width: 2vh; height: 2vh; right: 10px"></div>
        <hr style="position: absolute; top: 25%; width: 99.5%; border: 1px solid">
        <h1 style="position: absolute; top: 10vh; left: 2vh; font-size: 2vh; text-align: left">{{ chosenCard.cardDescription }}</h1>
        <div v-if="chosenCard.cardStatus">
          <hr v-if="chosenCard.cardStatus" style="position: absolute; top: 60%; width: 99.5%; border: 1px solid">
          <h1 v-if="chosenCard.cardStatus=='Bleeding' || chosenCard.cardStatus=='Adjacent Bleeding'" style="position: absolute; top: 75%; font-size: 2vh">{{ status[0] }}</h1>
          <h1 v-if="chosenCard.cardStatus=='Vitality'" style="position: absolute; top: 75%; font-size: 2vh">{{ status[1] }}</h1>
          <h1 v-if="chosenCard.cardStatus=='Shield'" style="position: absolute; top: 75%; font-size: 2vh">{{ status[2] }}</h1>
          <h1 v-if="chosenCard.cardStatus=='Freeze'" style="position: absolute; top: 75%; font-size: 2vh">{{ status[3] }}</h1>
        </div>
    </div> <!-- Chosen Card Description  --->
    <b-button v-if="chosenCard.cardName" @click="chosenCard={}; chosenPlayableCard={}" style="position: absolute; left: 70%; bottom: 10%;">close</b-button>
    <div v-if="!showStartGame" style="position: absolute; right: 1%; top: 48.5%;">
        <button v-if="isEnemyTurn" style="font-size: 2vh; height: 5vh; background-color: antiquewhite;">Enemy Turn</button>
        <button v-if="cardPlayed" @click="startEnemyTurn(); cardPlayed=false; isEnemyTurn=true" style="font-size: 2vh; height: 5vh; background-color: red;">End Turn</button>
        <button v-if="!cardPlayed && !isEnemyTurn && chosenCardPlayedCard!='Any Card From Own Deck' && !showTutoredCard && chosenCardTarget!='Manual' && !playerPlayed && !playerPassed" @click="playerPassed=true; checkRoundEnd(); chosenCard={}; chosenPlayableCard={}; chosenPlayableCardIndex=null" style="font-size: 2vh; height: 5vh; background-color: antiquewhite;">Pass</button>
    </div> <!-- Pass and End Turn --->
    <div style="position: absolute; right: 10%; top: 40;">{{ playerPlayed }}</div>
  </div>
</template>

<script lang="js">
import decks from "@/assets/decks.ts"
export default{
  data() {
      return {
          opponentScore: 0,
          playerScore: 0,
          opponentWonRound: false,
          playerWonRound: false,
          opponentWon: false,
          playerWon: false,
          opponentPassed: false,
          playerPassed: false,
          playerPlayed: false,
          playerStarts: false,
          isRedrawPhase: false,
          redrawnCards: [],
          gameResult: "",
          opponentBoard: [{}, {}, {}, {}, {}, {}, {}, {}, {}, {}],
          playerBoard: [{}, {}, {}, {}, {}, {}, {}, {}, {}, {}],
          opponentHand:  [{}, {}, {}, {}, {}, {}, {}, {}, {}, {}],
          playerHand: [{}, {}, {}, {}, {}, {}, {}, {}, {}, {}],
          opponentDeck: decks[1][2].deck,
          visibleDeck:[],
          playerGraveyard:[],
          opponentGraveyard:[],
          playerDeck: decks[0][2].deck,
          showStartGame: true,
          isEnemyTurn: false,
          cardPlayed: false,
          showDeck: false,
          showPlayerGraveyard: false,
          showOpponentGraveyard: false,
          showTutoredCard: false,
          chosenPlayableCard: {},
          chosenPlayableCardIndex: null,
          chosenCardHealth: null,
          chosenCardEffect: "",
          chosenCardEffectCondition: null,
          chosenCardRemovalCondition: null,
          chosenCardRemovalConditionValue: null,
          chosenCardTarget: "",
          chosenCardTargetType: "",
          chosenCardEffectValue: null,
          chosenCardStatus: "",
          chosenCardStatusDuration: null,
          chosenCardEngineEffect: "",
          chosenCardPlayedCard: "",
          chosenCardIndex: null,
          chosenCard: {},
          chosenCardRevealedNum: null,
          chosenEnemyPlayableCard: null,
          chosenEnemyPlayableCardIndex: null,
          chosenEnemyCardHealth: null,
          chosenEnemyCardStatusses: null,
          chosenEnemyCardEffect: "",
          chosenEnemyCardEffectCondition: null,
          chosenEnemyCardRemovalCondition: null,
          chosenEnemyCardRemovalConditionValue: null,
          chosenEnemyCardTarget: "",
          chosenEnemyCardTargetType: "",
          chosenEnemyCardEffectValue: null,
          chosenEnemyCardStatus: "",
          chosenEnemyCardStatusDuration: null,
          chosenEnemyCardEngineEffect: "",
          chosenEnemyCardPlayedCard: "",
          chosenEnemyCardIndex: null,
          chosenEnemyCardType: null,
          chosenEnemyCard: {},
          filledBoardSpace: [],
          alliedEngines: [],
          opponentEngines: [],
          cheifI: null,
          chiefI2: null,
          oppChiefI: null,
          oppChiefI2: null,
          spyI: null,
          spyI2: null,
          oppSpyI: null,
          oppSpyI2: null,
          filledOpponentBoardSpace: [],
          status: [
          "Bleeding: At the end of that unit's turn damage it by 1.",
          "Vitality: At the end of that unit's turn boost it by 1.",
          "Shield: Block a single instance of damage.",
          "Freeze: Disable the ability of a unit.",
          ],
      }
  },
  methods: {
      startGame(){
          this.playerDeck.sort(() => Math.random() - 0.5);
          for(let i = 0; i < 10; i++){
              let drawnCard = this.playerDeck.shift()
              drawnCard.revealed1 = false
              drawnCard.revealed2 = false
              drawnCard.revealed3 = false
              drawnCard.revealed4 = false
              if(drawnCard.revealedCount){drawnCard.revealedCount++}
              else{drawnCard.revealedCount=1}
              let chosenRevealed = null
              if(drawnCard.revealedCount==1){chosenRevealed=drawnCard.revealed1}
              else if(drawnCard.revealedCount==2){chosenRevealed=drawnCard.revealed2}
              else if(drawnCard.revealedCount==3){chosenRevealed=drawnCard.revealed3}
              else {chosenRevealed=drawnCard.revealed4}
              if(this.playerDeck.length){  
                this.playerHand[i] = {
                    cardName: drawnCard.cardName,
                    cardBaseHealth: drawnCard.cardBaseHealth,
                    cardEffect: drawnCard.cardEffect,
                    cardEffectCondition: drawnCard.cardEffectCondition,
                    cardEffectTarget: drawnCard.cardEffectTarget,
                    cardStatus: drawnCard.cardStatus,
                    cardStatus2: drawnCard.cardStatus2,
                    cardStatusDuration: drawnCard.cardStatusDuration,
                    cardStatusDuration2: drawnCard.cardStatusDuration2,
                    cardTargetUnitType: drawnCard.cardTargetUnitType,
                    cardTargetUnitType2: drawnCard.cardTargetUnitType2,
                    cardEffectValue: drawnCard.cardEffectValue,
                    cardEffect2: drawnCard.cardEffect2,
                    cardEffectTarget2: drawnCard.cardEffectTarget2,
                    cardEffectValue2: drawnCard.cardEffectValue2,
                    cardEngineType: drawnCard.cardEngineType,
                    cardEngineTarget: drawnCard.cardEngineTarget,
                    cardEngineValue: drawnCard.cardEngineValue,
                    cardEngineCondition: drawnCard.cardEngineCondition,
                    cardEngineType2: drawnCard.cardEngineType2,
                    cardEngineTarget2: drawnCard.cardEngineTarget2,
                    cardEngineValue2: drawnCard.cardEngineValue2,
                    cardEngineCondition2: drawnCard.cardEngineCondition2,
                    cardRandomness1: drawnCard.cardRandomness1,
                    cardRandomness2: drawnCard.cardRandomness2,
                    cardRemovalCondition: drawnCard.cardRemovalCondition,
                    cardRemovalConditionValue: drawnCard.cardRemovalConditionValue,
                    playedCard: drawnCard.playedCard,
                    consumeType: drawnCard.consumeType,
                    cardRarity: drawnCard.cardRarity,
                    cardDescription: drawnCard.cardDescription,
                    revealed: chosenRevealed,
            }}
          }
          this.visibleDeck = this.playerDeck;
          this.visibleDeck.sort(() => Math.random() - 0.5);
          this.opponentDeck.sort(() => Math.random() - 0.5);
          for(let o = 0; o < 10; o++){
              if(this.opponentDeck.length){
                let drawnCard = this.opponentDeck.shift()
                drawnCard.revealed1 = false
                drawnCard.revealed2 = false
                drawnCard.revealed3 = false
                drawnCard.revealed4 = false
                if(drawnCard.revealedCount){drawnCard.revealedCount++}
                else{drawnCard.revealedCount=1}
                let chosenRevealed = null
                if(drawnCard.revealedCount==1){chosenRevealed=drawnCard.revealed1}
                else if(drawnCard.revealedCount==2){chosenRevealed=drawnCard.revealed2}
                else if(drawnCard.revealedCount==3){chosenRevealed=drawnCard.revealed3}
                else {chosenRevealed=drawnCard.revealed4}
                this.opponentHand[o] = {
                    cardName: drawnCard.cardName,
                    cardBaseHealth: drawnCard.cardBaseHealth,
                    cardEffect: drawnCard.cardEffect,
                    cardEffectCondition: drawnCard.cardEffectCondition,
                    cardEffectTarget: drawnCard.cardEffectTarget,
                    cardStatus: drawnCard.cardStatus,
                    cardStatus2: drawnCard.cardStatus2,
                    cardStatusDuration: drawnCard.cardStatusDuration,
                    cardStatusDuration2: drawnCard.cardStatusDuration2,
                    cardTargetUnitType: drawnCard.cardTargetUnitType,
                    cardTargetUnitType2: drawnCard.cardTargetUnitType2,
                    cardEffectValue: drawnCard.cardEffectValue,
                    cardEffect2: drawnCard.cardEffect2,
                    cardEffectTarget2: drawnCard.cardEffectTarget2,
                    cardEffectValue2: drawnCard.cardEffectValue2,
                    cardEngineType: drawnCard.cardEngineType,
                    cardEngineTarget: drawnCard.cardEngineTarget,
                    cardEngineValue: drawnCard.cardEngineValue,
                    cardEngineCondition: drawnCard.cardEngineCondition,
                    cardEngineType2: drawnCard.cardEngineType2,
                    cardEngineTarget2: drawnCard.cardEngineTarget2,
                    cardEngineValue2: drawnCard.cardEngineValue2,
                    cardEngineCondition2: drawnCard.cardEngineCondition2,
                    cardRandomness1: drawnCard.cardRandomness1,
                    cardRandomness2: drawnCard.cardRandomness2,
                    cardRemovalCondition: drawnCard.cardRemovalCondition,
                    cardRemovalConditionValue: drawnCard.cardRemovalConditionValue,
                    playedCard: drawnCard.playedCard,
                    consumeType: drawnCard.consumeType,
                    cardRarity: drawnCard.cardRarity,
                    cardDescription: drawnCard.cardDescription,
                    revealed: chosenRevealed,
            }}
          }
          this.showStartGame = false;
          this.isRedrawPhase = true
      },
      playCard(boardI){
          for(let i = 0; i < this.playerDeck.length; i++){
              let isInDeck = false
              for(let o = 0; o < this.visibleDeck.length; o++){
                  if(this.playerDeck[i]==this.visibleDeck[o]){isInDeck=true}
              }
              if(isInDeck==false){this.playerDeck.splice(i, 1)}
          }
          for(let i = 0; i < this.visibleDeck.length; i++){
              let isInDeck = false
              for(let o = 0; o < this.playerDeck.length; o++){
                  if(this.visibleDeck[i]==this.playerDeck[o]){isInDeck=true}
              }
              if(isInDeck==false){this.visibleDeck.splice(i, 1)}
          }
          this.chosenCardTargetType = ""
          this.chosenCardEffect = this.chosenPlayableCard.cardEffect
          this.chosenCardEffectCondition = this.chosenPlayableCard.cardEffectCondition
          this.chosenCardTarget = this.chosenPlayableCard.cardEffectTarget
          this.chosenCardTargetType = this.chosenPlayableCard.cardTargetUnitType
          this.chosenCardEffectValue = this.chosenPlayableCard.cardEffectValue
          this.chosenCardStatus = this.chosenPlayableCard.cardStatus
          this.chosenCardStatusDuration = this.chosenPlayableCard.cardStatusDuration
          this.chosenCardEngineEffect = this.chosenPlayableCard.cardEngineType
          this.chosenCardRemovalCondition = this.chosenPlayableCard.cardRemovalCondition
          this.chosenCardRemovalConditionValue = this.chosenPlayableCard.cardRemovalConditionValue
          this.chosenCardPlayedCard = this.chosenPlayableCard.playedCard
          this.chosenCardIndex = boardI
          this.chosenCardHealth=0
          for(let i = 0; i<this.chosenPlayableCard.cardBaseHealth; i++){this.chosenCardHealth++}
          this.playerBoard[boardI] = {
              cardAmount: this.chosenPlayableCard.cardAmount,
              cardName: this.chosenPlayableCard.cardName,
              cardBaseHealth: this.chosenPlayableCard.cardBaseHealth,
              cardHealth: this.chosenCardHealth,
              cardEffect: this.chosenPlayableCard.cardEffect,
              cardEffectCondition: this.chosenPlayableCard.cardEffectCondition,
              cardEffectTarget: this.chosenPlayableCard.cardEffectTarget,
              cardStatus: this.chosenPlayableCard.cardStatus,
              cardStatus2: this.chosenPlayableCard.cardStatus2,
              cardStatusDuration: this.chosenPlayableCard.cardStatusDuration,
              cardStatusDuration2: this.chosenPlayableCard.cardStatusDuration,
              cardTargetUnitType: this.chosenPlayableCard.cardTargetUnitType,
              cardTargetUnitType2: this.chosenPlayableCard.cardTargetUnitType2,
              cardEffectValue: this.chosenPlayableCard.cardEffectValue,
              cardEffect2: this.chosenPlayableCard.cardEffect2,
              cardEffectTarget2: this.chosenPlayableCard.cardEffectTarget2,
              cardEffectValue2: this.chosenPlayableCard.cardEffectValue2,
              cardEngineType: this.chosenPlayableCard.cardEngineType,
              cardEngineTarget: this.chosenPlayableCard.cardEngineTarget,
              cardEngineValue: this.chosenPlayableCard.cardEngineValue,
              cardEngineCondition: this.chosenPlayableCard.cardEngineCondition,
              cardEngineType2: this.chosenPlayableCard.cardEngineType2,
              cardEngineTarget2: this.chosenPlayableCard.cardEngineTarget2,
              cardEngineValue2: this.chosenPlayableCard.cardEngineValue2,
              cardEngineCondition2: this.chosenPlayableCard.cardEngineCondition2,
              cardRandomness1: this.chosenPlayableCard.cardRandomness1,
              cardRandomness2: this.chosenPlayableCard.cardRandomness2,
              cardRemovalCondition: this.chosenPlayableCard.cardRemovalCondition,
              cardRemovalConditionValue: this.chosenPlayableCard.cardRemovalConditionValue,
              playedCard: this.chosenPlayableCard.playedCard,
              consumeType: this.chosenPlayableCard.consumeType,
              cardRarity: this.chosenPlayableCard.cardRarity,
              cardDescription: this.chosenPlayableCard.cardDescription,
              statusses: [{}, {}, {}, {}]
          }
          this.chosenPlayableCard.cardAmount++
          this.playerHand[this.chosenPlayableCardIndex]={};
          this.chosenCard={};
          this.chosenPlayableCard={},
          this.showTutoredCard=false
          this.filledBoardSpace.push(boardI)
          if(this.playerBoard[boardI].cardEffectTarget=="Left" && boardI==0){
              this.playerBoard[boardI].cardEffectTarget=""
              this.playerBoard[boardI].cardEffect=""
          }
          if(this.playerBoard[boardI].cardEffectTarget=="Right" && boardI==9){
              this.playerBoard[boardI].cardEffectTarget=""
              this.playerBoard[boardI].cardEffect=""
          }
          if(this.playerBoard[boardI].cardEffectTarget=="Adjacent" && boardI==0){
              this.playerBoard[boardI].cardEffectTarget="Right"
          }
          if(this.playerBoard[boardI].cardEffectTarget=="Adjacent" && boardI==9){
              this.playerBoard[boardI].cardEffectTarget="Left"
          }
          if(this.playerBoard[boardI].cardEngineTarget=="Left" && boardI==0){
              this.playerBoard[boardI].cardEngineTarget=""
              this.playerBoard[boardI].cardEffect=""
          }
          if(this.playerBoard[boardI].cardEngineTarget=="Right" && boardI==9){
              this.playerBoard[boardI].cardEngineTarget=""
              this.playerBoard[boardI].cardEffect=""
          }
          if(this.playerBoard[boardI].cardEngineTarget=="Adjacent" && boardI==0){
              this.playerBoard[boardI].cardEngineTarget="Right"
          }
          if(this.playerBoard[boardI].cardEngineTarget=="Adjacent" && boardI==9){
              this.playerBoard[boardI].cardEngineTarget="Left"
          }

          if(this.playerBoard[boardI].cardEffect!="Status" && this.playerBoard[boardI].cardEffectTarget!="Manual"){
                if(this.playerBoard[boardI].cardEffectCondition=="Random"){
                      let value
                      value = Math.floor(Math.random() * (this.playerBoard[boardI].cardRandomness2 - this.playerBoard[boardI].cardRandomness1)) + this.playerBoard[boardI].cardRandomness1
                      this.playerBoard[boardI].cardEffectValue = value
                }
                if(this.playerBoard[boardI].cardEffectCondition=="Twice The Number Of Card In Hand"){
                      let value = 0
                      for(let i = 0; i<10; i++){if(this.playerHand[i].cardName){value+=2}}
                      this.playerBoard[boardI].cardEffectValue = value
                }
              if(this.playerBoard[boardI].cardEffectTarget=="Self"){
                  if(this.playerBoard[boardI].cardEffect=="Damage") {
                    if(boardI!=9){if(this.playerBoard[boardI+1].cardEffect!="Unkillable"){this.playerBoard[boardI].cardHealth -= this.playerBoard[boardI].cardEffectValue}}
                    else{this.playerBoard[boardI].cardHealth -= this.playerBoard[boardI].cardEffectValue}
                    if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                    if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}
                    }
             else if(this.playerBoard[boardI].cardEffect=="Boost") {
                    this.playerBoard[boardI].cardHealth += this.playerBoard[boardI].cardEffectValue
                    if(this.oppSpyI!=null){this.opponentBoard[this.oppSpyI].cardHealth += this.playerBoard[boardI].cardEffectValue}
                    if(this.oppSpyI2!=null){this.opponentBoard[this.oppSpyI2].cardHealth += this.playerBoard[boardI].cardEffectValue}
                    }
       } else if(this.playerBoard[boardI].cardEffectTarget=="Left"){
                if(boardI!=0){if(this.playerBoard[boardI-1].cardName){
                    if(this.playerBoard[boardI].cardEffect=="Boost"){
                        this.playerBoard[boardI-1].cardHealth += this.playerBoard[boardI].cardEffectValue
                        if(this.oppSpyI!=null){this.opponentBoard[this.oppSpyI].cardHealth += this.playerBoard[boardI].cardEffectValue}
                        if(this.oppSpyI2!=null){this.opponentBoard[this.oppSpyI2].cardHealth += this.playerBoard[boardI].cardEffectValue}
                        if(this.playerBoard[boardI-1].cardEngineCondition=="Received Boost"){this.playerBoard[boardI-1].cardEngineValue++}
             } else if(this.playerBoard[boardI].cardEffect=="Damage"){
                        if(this.playerBoard[boardI-1].damageBondI){
                            this.playerBoard[this.playerBoard[this.playerBoard[boardI-1]].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue
                } else if(this.playerBoard[boardI-1].statusses[2].status=="Shield"){
                        this.playerBoard[boardI-1].statusses[2]={}
                    } else {
                        this.playerBoard[boardI-1].cardHealth -= this.playerBoard[boardI].cardEffectValue
                        if(this.playerBoard[boardI-1].cardEngineCondition=="Damage Taken"){this.playerBoard[boardI-1].cardEngineValue++}
                        if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                        if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}
                        }}}}
       } else if(this.playerBoard[boardI].cardEffectTarget=="Right"){
                if(boardI!=9){if(this.playerBoard[boardI+1].cardName){
                    if(this.playerBoard[boardI].cardEffect=="Boost"){
                        this.playerBoard[boardI+1].cardHealth += this.playerBoard[boardI].cardEffectValue
                        if(this.oppSpyI!=null){this.opponentBoard[this.oppSpyI].cardHealth += this.playerBoard[boardI].cardEffectValue}
                        if(this.oppSpyI2!=null){this.opponentBoard[this.oppSpyI2].cardHealth += this.playerBoard[boardI].cardEffectValue}
                        if(this.playerBoard[boardI+1].cardEngineCondition=="Received Boost"){this.playerBoard[boardI+1].cardEngineValue++}}
                else if(this.playerBoard[boardI].cardEffect=="Damage"){
                        if(this.playerBoard[boardI+1].damageBondI){
                            this.playerBoard[this.playerBoard[this.playerBoard[boardI+1]].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue
                } else if(this.playerBoard[boardI+1].statusses[2].status=="Shield"){
                        this.playerBoard[boardI+1].statusses[2]={}
                    } else {
                        if(boardI<8){if(this.playerBoard[boardI+2].cardEffect!="Unkillable"){this.playerBoard[boardI+1].cardHealth -= this.playerBoard[boardI].cardEffectValue}}
                        else{this.playerBoard[boardI+1].cardHealth -= this.playerBoard[boardI].cardEffectValue}
                        if(this.playerBoard[boardI+1].cardEngineCondition=="Damage Taken"){this.playerBoard[boardI+1].cardEngineValue++}
                        if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                        if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}}}
                }}
       } else if(this.playerBoard[boardI].cardEffectTarget=="Adjacent"){
                if(boardI!=0){if(this.playerBoard[boardI-1].cardName){
                    if(this.playerBoard[boardI].cardEffect=="Boost"){
                        this.playerBoard[boardI-1].cardHealth += this.playerBoard[boardI].cardEffectValue
                        if(this.oppSpyI!=null){this.opponentBoard[this.oppSpyI].cardHealth += this.playerBoard[boardI].cardEffectValue}
                        if(this.oppSpyI2!=null){this.opponentBoard[this.oppSpyI2].cardHealth += this.playerBoard[boardI].cardEffectValue}
                        if(this.playerBoard[boardI-1].cardEngineCondition=="Received Boost"){this.playerBoard[boardI-1].cardEngineValue++
                        }}
                else if(this.playerBoard[boardI].cardEffect=="Damage"){
                        if(this.playerBoard[boardI-1].damageBondI){
                            this.playerBoard[this.playerBoard[this.playerBoard[boardI-1]].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue
                } else if(this.playerBoard[boardI-1].statusses[2].status=="Shield"){
                        this.playerBoard[boardI-1].statusses[2]={}
                    } else {
                        this.playerBoard[boardI-1].cardHealth -= this.playerBoard[boardI].cardEffectValue
                        if(this.playerBoard[boardI-1].cardEngineCondition=="Damage Taken"){this.playerBoard[boardI-1].cardEngineValue++}
                        if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                        if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}
                        }}}}
                if(boardI!=9){if(this.playerBoard[boardI+1].cardName){        
                    if(this.playerBoard[boardI].cardEffect=="Boost"){
                        this.playerBoard[boardI+1].cardHealth += this.playerBoard[boardI].cardEffectValue
                        if(this.oppSpyI!=null){this.opponentBoard[this.oppSpyI].cardHealth += this.playerBoard[boardI].cardEffectValue}
                        if(this.oppSpyI2!=null){this.opponentBoard[this.oppSpyI2].cardHealth += this.playerBoard[boardI].cardEffectValue}
                        if(this.playerBoard[boardI+1].cardEngineCondition=="Received Boost"){this.playerBoard[boardI+1].cardEngineValue++
                        }}
                else if(this.playerBoard[boardI].cardEffect=="Damage"){
                        if(this.playerBoard[boardI+1].damageBondI){
                            this.playerBoard[this.playerBoard[this.playerBoard[boardI+1]].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue
                } else if(this.playerBoard[boardI+1].statusses[2].status=="Shield"){
                        this.playerBoard[boardI+1].statusses[2]={}
                    } else {
                        if(boardI<8){if(this.playerBoard[boardI+2].cardEffect!="Unkillable"){this.playerBoard[boardI+1].cardHealth -= this.playerBoard[boardI].cardEffectValue}}
                        else{this.playerBoard[boardI+1].cardHealth -= this.playerBoard[boardI].cardEffectValue}
                        if(this.playerBoard[boardI+1].cardEngineCondition=="Damage Taken"){this.playerBoard[boardI+1].cardEngineValue++}
                        if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                        if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}}}}}
       } else if(this.playerBoard[boardI].cardEffectTarget=="Random"){
                  if(this.playerBoard[boardI].cardTargetUnitType=="Ally"){
                      if(this.filledBoardSpace.length>0){
                          let unitI = this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]
                          if(this.playerBoard[boardI].cardEffect=="Boost"){
                            this.playerBoard[unitI].cardHealth += this.playerBoard[boardI].cardEffectValue
                            if(this.oppSpyI!=null){this.opponentBoard[this.oppSpyI].cardHealth += this.playerBoard[boardI].cardEffectValue}
                            if(this.oppSpyI2!=null){this.opponentBoard[this.oppSpyI2].cardHealth += this.playerBoard[boardI].cardEffectValue}
                            if(this.playerBoard[unitI].cardEngineCondition=="Received Boost"){this.playerBoard[unitI].cardEngineValue++}}
                     else if(this.playerBoard[boardI].cardEffect=="Damage"){
                            if(this.playerBoard[unitI].damageBondI){
                              this.playerBoard[this.playerBoard[unitI].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue
                     } else if(this.playerBoard[unitI].statusses[2].status=="Shield"){
                              this.playerBoard[unitI].statusses[2]={}
                     } else {
                         if(unitI!=9){if(this.playerBoard[unitI+1].cardEffect!="Unkillable"){this.playerBoard[unitI].cardHealth -= this.playerBoard[boardI].cardEffectValue}}
                         else{this.playerBoard[unitI].cardHealth -= this.playerBoard[boardI].cardEffectValue}
                         if(this.playerBoard[unitI].cardEngineCondition=="Damage Taken"){this.playerBoard[unitI].cardEngineValue++}
                         if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                         if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}}}
                        }
           } else if(this.playerBoard[boardI].cardTargetUnitType=="Enemy"){
                      if(this.filledOpponentBoardSpace.length>0){
                          let unitI = this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]
                          if(this.playerBoard[boardI].cardEffect=="Boost"){
                            this.opponentBoard[unitI].cardHealth += this.playerBoard[boardI].cardEffectValue
                            if(this.spyI!=null){this.playerBoard[this.spyI].cardHealth += this.playerBoard[boardI].cardEffectValue}
                            if(this.spyI2!=null){this.playerBoard[this.spyI2].cardHealth += this.playerBoard[boardI].cardEffectValue}
                            if(this.opponentBoard[unitI].cardEngineCondition=="Received Boost"){this.opponentBoard[unitI].cardEngineValue++}}
                     else if(this.playerBoard[boardI].cardEffect=="Damage"){
                            if(this.opponentBoard[unitI].damageBondI){
                              this.opponentBoard[this.opponentBoard[unitI].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue
                     } else if(this.opponentBoard[unitI].statusses[2].status=="Shield"){
                              this.opponentBoard[unitI].statusses[2]={}
                     } else {
                         if(unitI!=9){if(this.opponentBoard[unitI+1].cardEffect!="Unkillable"){this.opponentBoard[unitI].cardHealth -= this.playerBoard[boardI].cardEffectValue}}
                         else{this.opponentBoard[unitI].cardHealth -= this.playerBoard[boardI].cardEffectValue}
                         if(this.opponentBoard[unitI].cardEngineCondition=="Damage Taken"){this.opponentBoard[unitI].cardEngineValue++}
                         if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                         if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                    }}
                        }
           } else if(this.playerBoard[boardI].cardTargetUnitType=="All"){
                    let side = Math.floor(Math.random() * 2)
                    if(side == 0){
                       if(this.filledBoardSpace.length>0){
                          let unitI = this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]
                          if(this.playerBoard[boardI].cardEffect=="Boost"){
                            this.playerBoard[unitI].cardHealth += this.playerBoard[boardI].cardEffectValue
                            if(this.oppSpyI!=null){this.opponentBoard[this.oppSpyI].cardHealth += this.playerBoard[boardI].cardEffectValue}
                            if(this.oppSpyI2!=null){this.opponentBoard[this.oppSpyI2].cardHealth += this.playerBoard[boardI].cardEffectValue}
                            if(this.playerBoard[unitI].cardEngineCondition=="Received Boost"){this.playerBoard[unitI].cardEngineValue++}}
                     else if(this.playerBoard[boardI].cardEffect=="Damage"){
                            if(this.playerBoard[unitI].damageBondI){
                              this.playerBoard[this.playerBoard[unitI].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue
                     } else if(this.playerBoard[unitI].statusses[2].status=="Shield"){
                              this.playerBoard[unitI].statusses[2]={}
                     } else {
                         if(unitI!=9){if(this.playerBoard[unitI+1].cardEffect!="Unkillable"){this.playerBoard[unitI].cardHealth -= this.playerBoard[boardI].cardEffectValue}}
                         else{this.playerBoard[unitI].cardHealth -= this.playerBoard[boardI].cardEffectValue}
                         if(this.playerBoard[unitI].cardEngineCondition=="Damage Taken"){this.playerBoard[unitI].cardEngineValue++}
                         if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                         if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}}
                        }}
             } else if(side == 1){
                      if(this.filledOpponentBoardSpace.length>0){
                          let unitI = this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]
                          if(this.playerBoard[boardI].cardEffect=="Boost"){
                            this.opponentBoard[unitI].cardHealth += this.playerBoard[boardI].cardEffectValue
                            if(this.spyI!=null){this.playerBoard[this.spyI].cardHealth += this.playerBoard[boardI].cardEffectValue}
                            if(this.spyI2!=null){this.playerBoard[this.spyI2].cardHealth += this.playerBoard[boardI].cardEffectValue}
                            if(this.opponentBoard[unitI].cardEngineCondition=="Received Boost"){this.opponentBoard[unitI].cardEngineValue++}}
                     else if(this.playerBoard[boardI].cardEffect=="Damage"){
                            if(this.opponentBoard[unitI].damageBondI){
                              this.opponentBoard[this.opponentBoard[unitI].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue
                     } else if(this.opponentBoard[unitI].statusses[2].status=="Shield"){
                              this.opponentBoard[unitI].statusses[2]={}
                     } else {
                         if(unitI!=9){if(this.opponentBoard[unitI+1].cardEffect!="Unkillable"){this.opponentBoard[unitI].cardHealth -= this.playerBoard[boardI].cardEffectValue}}
                         else{this.opponentBoard[unitI].cardHealth -= this.playerBoard[boardI].cardEffectValue}
                         if(this.opponentBoard[unitI].cardEngineCondition=="Damage Taken"){this.opponentBoard[unitI].cardEngineValue++}
                         if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                         if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                    }}
                }
             }
           }
       } else if(this.playerBoard[boardI].cardEffectTarget=="All Allies"){
           for(let i = 0; i < this.filledBoardSpace.length; i++){
               if(this.playerBoard[boardI].cardEffect=="Boost"){
                    this.playerBoard[this.filledBoardSpace[i]].cardHealth += this.playerBoard[boardI].cardEffectValue
                    if(this.oppSpyI!=null){this.opponentBoard[this.oppSpyI].cardHealth += this.playerBoard[boardI].cardEffectValue}
                    if(this.oppSpyI2!=null){this.opponentBoard[this.oppSpyI2].cardHealth += this.playerBoard[boardI].cardEffectValue}
                    if(this.playerBoard[this.filledBoardSpace[i]].cardEngineCondition=="Received Boost"){this.playerBoard[this.filledBoardSpace[i]].cardEngineValue++}}
             else if(this.playerBoard[boardI].cardEffect=="Damage"){
                    if(this.playerBoard[this.filledBoardSpace[i]].damageBondI){
                        this.playerBoard[this.playerBoard[this.playerBoard[this.filledBoardSpace[i]]].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue
             } else if(this.playerBoard[this.filledBoardSpace[i]].statusses[2].status=="Shield"){
                      this.playerBoard[this.filledBoardSpace[i]].statusses[2]={}
                  } else {
                      if(this.filledBoardSpace[i]!=9){if(this.playerBoard[this.filledBoardSpace[i]+1].cardEffect!="Unkillable"){this.playerBoard[this.filledBoardSpace[i]].cardHealth -= this.playerBoard[boardI].cardEffectValue}}
                      else{this.playerBoard[this.filledBoardSpace[i]].cardHealth -= this.playerBoard[boardI].cardEffectValue}
                      if(this.playerBoard[this.filledBoardSpace[i]].cardEngineCondition=="Damage Taken"){this.playerBoard[this.filledBoardSpace[i]].cardEngineValue++}
                      if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                      if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}}}
           }
       } else if(this.playerBoard[boardI].cardEffectTarget=="All Enemies"){
           for(let i = 0; i < this.filledOpponentBoardSpace.length; i++){
               if(this.playerBoard[boardI].cardEffect=="Boost"){
                    this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth += this.playerBoard[boardI].cardEffectValue
                    if(this.spyI!=null){this.playerBoard[this.spyI].cardHealth += this.playerBoard[boardI].cardEffectValue}
                    if(this.spyI2!=null){this.playerBoard[this.spyI2].cardHealth += this.playerBoard[boardI].cardEffectValue}
                    if(this.opponentBoard[this.filledOpponentBoardSpace[i]].cardEngineCondition=="Received Boost"){this.opponentBoard[this.filledOpponentBoardSpace[i]].cardEngineValue++}}
          else if(this.playerBoard[boardI].cardEffect=="Damage"){
                    if(this.opponentBoard[this.filledOpponentBoardSpace[i]].damageBondI){
                        this.opponentBoard[this.opponentBoard[this.opponentBoard[this.filledOpponentBoardSpace[i]]].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue
             } else if(this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[2].status=="Shield"){
                      this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[2]={}
                  } else {
                      if(this.filledOpponentBoardSpace[i]!=9){if(this.opponentBoard[this.filledOpponentBoardSpace[i]+1].cardName != null || this.opponentBoard[this.filledOpponentBoardSpace[i]+1].cardEffect!="Unkillable"){this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth -= this.playerBoard[boardI].cardEffectValue}}
                      else{this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth -= this.playerBoard[boardI].cardEffectValue}
                      if(this.opponentBoard[this.filledOpponentBoardSpace[i]].cardEngineCondition=="Damage Taken"){this.opponentBoard[this.filledOpponentBoardSpace[i]].cardEngineValue++}
                      if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                      if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                    }}
           }
          }}
          if(this.playerBoard[boardI].cardEffect2!="Status" && this.playerBoard[boardI].cardEffectTarget2!="Manual"){
                if(this.playerBoard[boardI].cardEffectCondition2=="Random"){
                      let value
                      value = Math.floor(Math.random() * (this.playerBoard[boardI].cardRandomness2 - this.playerBoard[boardI].cardRandomness1)) + this.playerBoard[boardI].cardRandomness1
                      this.playerBoard[boardI].cardEffectValue2 = value
                }
                if(this.playerBoard[boardI].cardEffectCondition2=="Twice The Number Of Card In Hand"){
                      let value = 0
                      for(let i = 0; i<10; i++){if(this.playerHand[i].cardName){value+=2}}
                      this.playerBoard[boardI].cardEffectValue2 = value
                }
              if(this.playerBoard[boardI].cardEffectTarget2=="Self"){
                  if(this.playerBoard[boardI].cardEffect2=="Damage") {
                    if(boardI!=9){if(this.playerBoard[boardI+1].cardEffect!="Unkillable"){this.playerBoard[boardI].cardHealth -= this.playerBoard[boardI].cardEffectValue2}}
                    else{this.playerBoard[boardI].cardHealth -= this.playerBoard[boardI].cardEffectValue2}
                    if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                    if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}
                    }
             else if(this.playerBoard[boardI].cardEffect2=="Boost") {
                    this.playerBoard[boardI].cardHealth += this.playerBoard[boardI].cardEffectValue2
                    if(this.oppSpyI!=null){this.opponentBoard[this.oppSpyI].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                    if(this.oppSpyI2!=null){this.opponentBoard[this.oppSpyI2].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                    }
       } else if(this.playerBoard[boardI].cardEffectTarget2=="Left"){
                if(boardI!=0){if(this.playerBoard[boardI-1].cardName){
                    if(this.playerBoard[boardI].cardEffect2=="Boost"){
                        this.playerBoard[boardI-1].cardHealth += this.playerBoard[boardI].cardEffectValue2
                        if(this.oppSpyI!=null){this.opponentBoard[this.oppSpyI].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                        if(this.oppSpyI2!=null){this.opponentBoard[this.oppSpyI2].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                        if(this.playerBoard[boardI-1].cardEngineCondition=="Received Boost"){this.playerBoard[boardI-1].cardEngineValue++}
             } else if(this.playerBoard[boardI].cardEffect2=="Damage"){
                        if(this.playerBoard[boardI-1].damageBondI){
                            this.playerBoard[this.playerBoard[this.playerBoard[boardI-1]].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue2
                } else if(this.playerBoard[boardI-1].statusses[2].status=="Shield"){
                        this.playerBoard[boardI-1].statusses[2]={}
                    } else {
                        this.playerBoard[boardI-1].cardHealth -= this.playerBoard[boardI].cardEffectValue2
                        if(this.playerBoard[boardI-1].cardEngineCondition=="Damage Taken"){this.playerBoard[boardI-1].cardEngineValue++}
                        if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                        if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}
                        }}}}
       } else if(this.playerBoard[boardI].cardEffectTarget2=="Right"){
                if(boardI!=9){if(this.playerBoard[boardI+1].cardName){
                    if(this.playerBoard[boardI].cardEffect2=="Boost"){
                        this.playerBoard[boardI+1].cardHealth += this.playerBoard[boardI].cardEffectValue2
                        if(this.oppSpyI!=null){this.opponentBoard[this.oppSpyI].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                        if(this.oppSpyI2!=null){this.opponentBoard[this.oppSpyI2].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                        if(this.playerBoard[boardI+1].cardEngineCondition=="Received Boost"){this.playerBoard[boardI+1].cardEngineValue++}}
                else if(this.playerBoard[boardI].cardEffect2=="Damage"){
                        if(this.playerBoard[boardI+1].damageBondI){
                            this.playerBoard[this.playerBoard[this.playerBoard[boardI+1]].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue2
                } else if(this.playerBoard[boardI+1].statusses[2].status=="Shield"){
                        this.playerBoard[boardI+1].statusses[2]={}
                    } else {
                        if(boardI<8){if(this.playerBoard[boardI+2].cardEffect!="Unkillable"){this.playerBoard[boardI+1].cardHealth -= this.playerBoard[boardI].cardEffectValue2}}
                        else{this.playerBoard[boardI+1].cardHealth -= this.playerBoard[boardI].cardEffectValue2}
                        if(this.playerBoard[boardI+1].cardEngineCondition=="Damage Taken"){this.playerBoard[boardI+1].cardEngineValue++}
                        if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                        if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}}}
                }}
       } else if(this.playerBoard[boardI].cardEffectTarget2=="Adjacent"){
                if(boardI!=0){if(this.playerBoard[boardI-1].cardName){
                    if(this.playerBoard[boardI].cardEffect2=="Boost"){
                        this.playerBoard[boardI-1].cardHealth += this.playerBoard[boardI].cardEffectValue2
                        if(this.oppSpyI!=null){this.opponentBoard[this.oppSpyI].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                        if(this.oppSpyI2!=null){this.opponentBoard[this.oppSpyI2].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                        if(this.playerBoard[boardI-1].cardEngineCondition=="Received Boost"){this.playerBoard[boardI-1].cardEngineValue++
                        }}
                else if(this.playerBoard[boardI].cardEffect2=="Damage"){
                        if(this.playerBoard[boardI-1].damageBondI){
                            this.playerBoard[this.playerBoard[this.playerBoard[boardI-1]].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue2
                } else if(this.playerBoard[boardI-1].statusses[2].status=="Shield"){
                        this.playerBoard[boardI-1].statusses[2]={}
                    } else {
                        this.playerBoard[boardI-1].cardHealth -= this.playerBoard[boardI].cardEffectValue2
                        if(this.playerBoard[boardI-1].cardEngineCondition=="Damage Taken"){this.playerBoard[boardI-1].cardEngineValue++}
                        if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                        if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}
                        }}}}
                if(boardI!=9){if(this.playerBoard[boardI+1].cardName){        
                    if(this.playerBoard[boardI].cardEffect2=="Boost"){
                        this.playerBoard[boardI+1].cardHealth += this.playerBoard[boardI].cardEffectValue2
                        if(this.oppSpyI!=null){this.opponentBoard[this.oppSpyI].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                        if(this.oppSpyI2!=null){this.opponentBoard[this.oppSpyI2].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                        if(this.playerBoard[boardI+1].cardEngineCondition=="Received Boost"){this.playerBoard[boardI+1].cardEngineValue++
                        }}
                else if(this.playerBoard[boardI].cardEffect2=="Damage"){
                        if(this.playerBoard[boardI+1].damageBondI){
                            this.playerBoard[this.playerBoard[this.playerBoard[boardI+1]].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue2
                } else if(this.playerBoard[boardI+1].statusses[2].status=="Shield"){
                        this.playerBoard[boardI+1].statusses[2]={}
                    } else {
                        if(boardI<8){if(this.playerBoard[boardI+2].cardEffect!="Unkillable"){this.playerBoard[boardI+1].cardHealth -= this.playerBoard[boardI].cardEffectValue2}}
                        else{this.playerBoard[boardI+1].cardHealth -= this.playerBoard[boardI].cardEffectValue2}
                        if(this.playerBoard[boardI+1].cardEngineCondition=="Damage Taken"){this.playerBoard[boardI+1].cardEngineValue++}
                        if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                        if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}}}}}
       } else if(this.playerBoard[boardI].cardEffectTarget2=="Random"){
                  if(this.playerBoard[boardI].cardTargetUnitType2=="Ally"){
                      if(this.filledBoardSpace.length>0){
                          let unitI = this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]
                          if(this.playerBoard[boardI].cardEffect2=="Boost"){
                            this.playerBoard[unitI].cardHealth += this.playerBoard[boardI].cardEffectValue2
                            if(this.oppSpyI!=null){this.opponentBoard[this.oppSpyI].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                            if(this.oppSpyI2!=null){this.opponentBoard[this.oppSpyI2].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                            if(this.playerBoard[unitI].cardEngineCondition=="Received Boost"){this.playerBoard[unitI].cardEngineValue++}}
                     else if(this.playerBoard[boardI].cardEffect2=="Damage"){
                            if(this.playerBoard[unitI].damageBondI){
                              this.playerBoard[this.playerBoard[unitI].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue2
                     } else if(this.playerBoard[unitI].statusses[2].status=="Shield"){
                              this.playerBoard[unitI].statusses[2]={}
                     } else {
                         if(unitI!=9){if(this.playerBoard[unitI+1].cardEffect!="Unkillable"){this.playerBoard[unitI].cardHealth -= this.playerBoard[boardI].cardEffectValue2}}
                         else{this.playerBoard[unitI].cardHealth -= this.playerBoard[boardI].cardEffectValue2}
                         if(this.playerBoard[unitI].cardEngineCondition=="Damage Taken"){this.playerBoard[unitI].cardEngineValue++}
                         if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                         if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}}}
                        }
           } else if(this.playerBoard[boardI].cardTargetUnitType2=="Enemy"){
                      if(this.filledOpponentBoardSpace.length>0){
                          let unitI = this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]
                          if(this.playerBoard[boardI].cardEffect2=="Boost"){
                            this.opponentBoard[unitI].cardHealth += this.playerBoard[boardI].cardEffectValue
                            if(this.spyI!=null){this.playerBoard[this.spyI].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                            if(this.spyI2!=null){this.playerBoard[this.spyI2].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                            if(this.opponentBoard[unitI].cardEngineCondition=="Received Boost"){this.opponentBoard[unitI].cardEngineValue++}}
                     else if(this.playerBoard[boardI].cardEffect2=="Damage"){
                            if(this.opponentBoard[unitI].damageBondI){
                              this.opponentBoard[this.opponentBoard[unitI].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue2
                     } else if(this.opponentBoard[unitI].statusses[2].status=="Shield"){
                              this.opponentBoard[unitI].statusses[2]={}
                     } else {
                         if(unitI!=9){if(this.opponentBoard[unitI+1].cardEffect!="Unkillable"){this.opponentBoard[unitI].cardHealth -= this.playerBoard[boardI].cardEffectValue2}}
                         else{this.opponentBoard[unitI].cardHealth -= this.playerBoard[boardI].cardEffectValue2}
                         if(this.opponentBoard[unitI].cardEngineCondition=="Damage Taken"){this.opponentBoard[unitI].cardEngineValue++}
                         if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                         if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                    }}
                        }
           } else if(this.playerBoard[boardI].cardTargetUnitType2=="All"){
                    let side = Math.floor(Math.random() * 2)
                    if(side == 0){
                       if(this.filledBoardSpace.length>0){
                          let unitI = this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]
                          if(this.playerBoard[boardI].cardEffect2=="Boost"){
                            this.playerBoard[unitI].cardHealth += this.playerBoard[boardI].cardEffectValue2
                            if(this.oppSpyI!=null){this.opponentBoard[this.oppSpyI].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                            if(this.oppSpyI2!=null){this.opponentBoard[this.oppSpyI2].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                            if(this.playerBoard[unitI].cardEngineCondition=="Received Boost"){this.playerBoard[unitI].cardEngineValue++}}
                     else if(this.playerBoard[boardI].cardEffect2=="Damage"){
                            if(this.playerBoard[unitI].damageBondI){
                              this.playerBoard[this.playerBoard[unitI].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue2
                     } else if(this.playerBoard[unitI].statusses[2].status=="Shield"){
                              this.playerBoard[unitI].statusses[2]={}
                     } else {
                         if(unitI!=9){if(this.playerBoard[unitI+1].cardEffect!="Unkillable"){this.playerBoard[unitI].cardHealth -= this.playerBoard[boardI].cardEffectValue2}}
                         else{this.playerBoard[unitI].cardHealth -= this.playerBoard[boardI].cardEffectValue2}
                         if(this.playerBoard[unitI].cardEngineCondition=="Damage Taken"){this.playerBoard[unitI].cardEngineValue++}
                         if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                         if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}}
                        }}
             } else if(side == 1){
                      if(this.filledOpponentBoardSpace.length>0){
                          let unitI = this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]
                          if(this.playerBoard[boardI].cardEffect2=="Boost"){
                            this.opponentBoard[unitI].cardHealth += this.playerBoard[boardI].cardEffectValue
                            if(this.spyI!=null){this.playerBoard[this.spyI].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                            if(this.spyI2!=null){this.playerBoard[this.spyI2].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                            if(this.opponentBoard[unitI].cardEngineCondition=="Received Boost"){this.opponentBoard[unitI].cardEngineValue++}}
                     else if(this.playerBoard[boardI].cardEffect2=="Damage"){
                            if(this.opponentBoard[unitI].damageBondI){
                              this.opponentBoard[this.opponentBoard[unitI].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue2
                     } else if(this.opponentBoard[unitI].statusses[2].status=="Shield"){
                              this.opponentBoard[unitI].statusses[2]={}
                     } else {
                         if(unitI!=9){if(this.opponentBoard[unitI+1].cardEffect!="Unkillable"){this.opponentBoard[unitI].cardHealth -= this.playerBoard[boardI].cardEffectValue2}}
                         else{this.opponentBoard[unitI].cardHealth -= this.playerBoard[boardI].cardEffectValue2}
                         if(this.opponentBoard[unitI].cardEngineCondition=="Damage Taken"){this.opponentBoard[unitI].cardEngineValue++}
                         if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                         if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                    }}
                }
             }
           }
       } else if(this.playerBoard[boardI].cardEffectTarget2=="All Allies"){
           for(let i = 0; i < this.filledBoardSpace.length; i++){
               if(this.playerBoard[boardI].cardEffect2=="Boost"){
                    this.playerBoard[this.filledBoardSpace[i]].cardHealth += this.playerBoard[boardI].cardEffectValue2
                    if(this.oppSpyI!=null){this.opponentBoard[this.oppSpyI].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                    if(this.oppSpyI2!=null){this.opponentBoard[this.oppSpyI2].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                    if(this.playerBoard[this.filledBoardSpace[i]].cardEngineCondition=="Received Boost"){this.playerBoard[this.filledBoardSpace[i]].cardEngineValue++}}
             else if(this.playerBoard[boardI].cardEffect2=="Damage"){
                    if(this.playerBoard[this.filledBoardSpace[i]].damageBondI){
                        this.playerBoard[this.playerBoard[this.playerBoard[this.filledBoardSpace[i]]].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue2
             } else if(this.playerBoard[this.filledBoardSpace[i]].statusses[2].status=="Shield"){
                      this.playerBoard[this.filledBoardSpace[i]].statusses[2]={}
                  } else {
                      if(this.filledBoardSpace[i]!=9){if(this.playerBoard[this.filledBoardSpace[i]+1].cardEffect!="Unkillable"){this.playerBoard[this.filledBoardSpace[i]].cardHealth -= this.playerBoard[boardI].cardEffectValue2}}
                      else{this.playerBoard[this.filledBoardSpace[i]].cardHealth -= this.playerBoard[boardI].cardEffectValue2}
                      if(this.playerBoard[this.filledBoardSpace[i]].cardEngineCondition=="Damage Taken"){this.playerBoard[this.filledBoardSpace[i]].cardEngineValue++}
                      if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                      if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}}}
           }
       } else if(this.playerBoard[boardI].cardEffectTarget2=="All Enemies"){
           for(let i = 0; i < this.filledOpponentBoardSpace.length; i++){
               if(this.playerBoard[boardI].cardEffect2=="Boost"){
                    this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth += this.playerBoard[boardI].cardEffectValue2
                    if(this.spyI!=null){this.playerBoard[this.spyI].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                    if(this.spyI2!=null){this.playerBoard[this.spyI2].cardHealth += this.playerBoard[boardI].cardEffectValue2}
                    if(this.opponentBoard[this.filledOpponentBoardSpace[i]].cardEngineCondition=="Received Boost"){this.opponentBoard[this.filledOpponentBoardSpace[i]].cardEngineValue++}}
          else if(this.playerBoard[boardI].cardEffect2=="Damage"){
                    if(this.opponentBoard[this.filledOpponentBoardSpace[i]].damageBondI){
                        this.opponentBoard[this.opponentBoard[this.opponentBoard[this.filledOpponentBoardSpace[i]]].damageBondI].cardHealth -= this.playerBoard[boardI].cardEffectValue2
             } else if(this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[2].status=="Shield"){
                      this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[2]={}
                  } else {
                      if(this.filledOpponentBoardSpace[i]!=9){if(this.opponentBoard[this.filledOpponentBoardSpace[i]+1].cardName != null || this.opponentBoard[this.filledOpponentBoardSpace[i]+1].cardEffect!="Unkillable"){this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth -= this.playerBoard[boardI].cardEffectValue2}}
                      else{this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth -= this.playerBoard[boardI].cardEffectValue2}
                      if(this.opponentBoard[this.filledOpponentBoardSpace[i]].cardEngineCondition=="Damage Taken"){this.opponentBoard[this.filledOpponentBoardSpace[i]].cardEngineValue++}
                      if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                      if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                    }}
           }
          }}
          if(this.playerBoard[boardI].cardEffect=="Status" && this.playerBoard[boardI].cardEffectTarget!="Manual"){
              let duration = 0
              if(this.playerBoard[boardI].cardStatusDuration){duration = this.playerBoard[boardI].cardStatusDuration}
              if(this.playerBoard[boardI].cardEffectTarget=="Self"){
                if(this.playerBoard[boardI].cardStatus=="Bleeding"){
                    if(this.playerBoard[boardI].statusses[0].duration && this.playerBoard[boardI].statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + this.playerBoard[boardI].statusses[0].duration}   
                    this.playerBoard[boardI].statusses[0] = {status: this.playerBoard[boardI].cardStatus, duration}
         } else if(this.playerBoard[boardI].cardStatus=="Vitality"){
                    if(this.playerBoard[boardI].statusses[1].duration && this.playerBoard[boardI].statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + this.playerBoard[boardI].statusses[1].duration}   
                    this.playerBoard[boardI].statusses[1] = {status: this.playerBoard[boardI].cardStatus, duration}
         } else if(this.playerBoard[boardI].cardStatus=="Shield"){this.playerBoard[boardI].statusses[2] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
           else if(this.playerBoard[boardI].cardStatus=="Freeze"){this.playerBoard[boardI].statusses[3] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
       } else if(this.playerBoard[boardI].cardEffectTarget=="Left"){
                if(boardI!=0){if(this.playerBoard[boardI-1].cardName){
                  if(this.playerBoard[boardI].cardStatus=="Bleeding"){
                    if(this.playerBoard[boardI-1].statusses[0].duration && this.playerBoard[boardI-1].statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + this.playerBoard[boardI-1].statusses[0].duration}   
                    this.playerBoard[boardI-1].statusses[0] = {status: this.playerBoard[boardI].cardStatus, duration}
           } else if(this.playerBoard[boardI].cardStatus=="Vitality"){
                    if(this.playerBoard[boardI-1].statusses[1].duration && this.playerBoard[boardI-1].statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + this.playerBoard[boardI-1].statusses[1].duration}   
                    this.playerBoard[boardI-1].statusses[1] = {status: this.playerBoard[boardI].cardStatus, duration}
           } else if(this.playerBoard[boardI].cardStatus=="Shield"){this.playerBoard[boardI-1].statusses[2] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
             else if(this.playerBoard[boardI].cardStatus=="Freeze"){this.playerBoard[boardI-1].statusses[3] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
                }}
       } else if(this.playerBoard[boardI].cardEffectTarget=="Right"){
                  if(boardI!=9){if(this.playerBoard[boardI+1].cardName){
                    if(this.playerBoard[boardI].cardStatus=="Bleeding"){
                    if(this.playerBoard[boardI+1].statusses[0].duration && this.playerBoard[boardI+1].statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + this.playerBoard[boardI+1].statusses[0].duration}   
                    this.playerBoard[boardI+1].statusses[0] = {status: this.playerBoard[boardI].cardStatus, duration}
             } else if(this.playerBoard[boardI].cardStatus=="Vitality"){
                    if(this.playerBoard[boardI+1].statusses[1].duration && this.playerBoard[boardI+1].statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + this.playerBoard[boardI+1].statusses[1].duration}   
                    this.playerBoard[boardI+1].statusses[1] = {status: this.playerBoard[boardI].cardStatus, duration}
             } else if(this.playerBoard[boardI].cardStatus=="Shield"){this.playerBoard[boardI + 1].statusses[2] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
               else if(this.playerBoard[boardI].cardStatus=="Freeze"){this.playerBoard[boardI + 1].statusses[3] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
                }}
       } else if(this.playerBoard[boardI].cardEffectTarget=="Adjacent"){
                 if(boardI!=0){if(this.playerBoard[boardI-1].cardName){
                   if(this.playerBoard[boardI].cardStatus=="Bleeding"){
                    if(this.playerBoard[boardI-1].statusses[0].duration && this.playerBoard[boardI-1].statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + this.playerBoard[boardI-1].statusses[0].duration}   
                    this.playerBoard[boardI-1].statusses[0] = {status: this.playerBoard[boardI].cardStatus, duration}
            } else if(this.playerBoard[boardI].cardStatus=="Vitality"){
                    if(this.playerBoard[boardI-1].statusses[1].duration && this.playerBoard[boardI-1].statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + this.playerBoard[boardI-1].statusses[1].duration}   
                    this.playerBoard[boardI-1].statusses[1] = {status: this.playerBoard[boardI].cardStatus, duration}
            } else if(this.playerBoard[boardI].cardStatus=="Shield"){this.playerBoard[boardI - 1].statusses[2] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
              else if(this.playerBoard[boardI].cardStatus=="Freeze"){this.playerBoard[boardI - 1].statusses[3] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
                }}
                 if(boardI!=9){if(this.playerBoard[boardI+1].cardName){
                   if(this.playerBoard[boardI].cardStatus=="Bleeding"){
                    if(this.playerBoard[boardI+1].statusses[0].duration && this.playerBoard[boardI+1].statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + this.playerBoard[boardI+1].statusses[0].duration}   
                    this.playerBoard[boardI+1].statusses[0] = {status: this.playerBoard[boardI].cardStatus, duration}
            } else if(this.playerBoard[boardI].cardStatus=="Vitality"){
                    if(this.playerBoard[boardI+1].statusses[1].duration && this.playerBoard[boardI+1].statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + this.playerBoard[boardI+1].statusses[1].duration}   
                    this.playerBoard[boardI+1].statusses[1] = {status: this.playerBoard[boardI].cardStatus, duration}
            } else if(this.playerBoard[boardI].cardStatus=="Shield"){this.playerBoard[boardI + 1].statusses[2] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
              else if(this.playerBoard[boardI].cardStatus=="Freeze"){this.playerBoard[boardI + 1].statusses[3] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
                }}
       } else if(this.playerBoard[boardI].cardEffectTarget=="Random"){
                  if(this.playerBoard[boardI].cardTargetUnitType=="Ally"){
                      if(this.filledBoardSpace.length>0){
                          let unit = this.playerBoard[this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]]
                          if(this.playerBoard[boardI].cardStatus=="Bleeding"){
                    if(unit.statusses[0].duration && unit.statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + unit.statusses[0].duration}   
                    unit.statusses[0] = {status: this.playerBoard[boardI].cardStatus, duration}
                   } else if(this.playerBoard[boardI].cardStatus=="Vitality"){
                    if(unit.statusses[1].duration && unit.statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + unit.statusses[1].duration}   
                    unit.statusses[1] = {status: this.playerBoard[boardI].cardStatus, duration}
                   } else if(this.playerBoard[boardI].cardStatus=="Shield"){unit.statusses[2] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
                     else if(this.playerBoard[boardI].cardStatus=="Freeze"){unit.statusses[3] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
                        }
           } else if(this.playerBoard[boardI].cardTargetUnitType=="Enemy") {
                      if(this.filledOpponentBoardSpace.length>0){
                          let unit = this.opponentBoard[this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]]
                          if(this.playerBoard[boardI].cardStatus=="Bleeding"){
                    if(unit.statusses[0].duration && unit.statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + unit.statusses[0].duration}   
                    unit.statusses[0] = {status: this.playerBoard[boardI].cardStatus, duration}
                   } else if(this.playerBoard[boardI].cardStatus=="Vitality"){
                    if(unit.statusses[1].duration && unit.statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + unit.statusses[1].duration}   
                    unit.statusses[1] = {status: this.playerBoard[boardI].cardStatus, duration}
                   } else if(this.playerBoard[boardI].cardStatus=="Shield"){unit.statusses[2] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
                     else if(this.playerBoard[boardI].cardStatus=="Freeze"){unit.statusses[3] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
                        }
           } else if(this.playerBoard[boardI].cardTargetUnitType=="All"){
                    let side = Math.floor(Math.random() * 2)
                    let unit
                    if(side == 0){
                          unit = this.playerBoard[this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]]
             } else if(side == 1){
                          unit = this.opponentBoard[this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]]
             }      if(this.playerBoard[boardI].cardStatus=="Bleeding"){
                    if(unit.statusses[0].duration && unit.statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + unit.statusses[0].duration}   
                    unit.statusses[0] = {status: this.playerBoard[boardI].cardStatus, duration}
             } else if(this.playerBoard[boardI].cardStatus=="Vitality"){
                    if(unit.statusses[1].duration && unit.statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + unit.statusses[1].duration}   
                    unit.statusses[1] = {status: this.playerBoard[boardI].cardStatus, duration}
             } else if(this.playerBoard[boardI].cardStatus=="Shield"){unit.statusses[2] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
               else if(this.playerBoard[boardI].cardStatus=="Freeze"){unit.statusses[3] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
           }
       } else if(this.playerBoard[boardI].cardEffectTarget=="All Allies"){
           for(let i = 0; i < this.filledBoardSpace.length; i++){
                 if(this.playerBoard[boardI].cardStatus=="Bleeding"){
                    if(this.playerBoard[this.filledBoardSpace[i]].statusses[0].duration && this.playerBoard[this.filledBoardSpace[i]].statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + this.playerBoard[this.filledBoardSpace[i]].statusses[0].duration}   
                    this.playerBoard[this.filledBoardSpace[i]].statusses[0] = {status: this.playerBoard[boardI].cardStatus, duration}
          } else if(this.playerBoard[boardI].cardStatus=="Vitality"){
                    if(this.playerBoard[this.filledBoardSpace[i]].statusses[1].duration && this.playerBoard[this.filledBoardSpace[i]].statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + this.playerBoard[this.filledBoardSpace[i]].statusses[1].duration}   
                    this.playerBoard[this.filledBoardSpace[i]].statusses[1] = {status: this.playerBoard[boardI].cardStatus, duration}
          } else if(this.playerBoard[boardI].cardStatus=="Shield"){this.playerBoard[this.filledBoardSpace[i]].statusses[2] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
            else if(this.playerBoard[boardI].cardStatus=="Freeze"){this.playerBoard[this.filledBoardSpace[i]].statusses[3] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
            if(this.playerBoard[boardI].cardStatusDuration){duration = this.playerBoard[boardI].cardStatusDuration}
           }
       } else if(this.playerBoard[boardI].cardEffectTarget=="All Enemies"){
           for(let i = 0; i < this.filledOpponentBoardSpace.length; i++){
                if(this.playerBoard[boardI].cardStatus=="Bleeding"){
                    if(this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0].duration && this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0].duration}   
                    this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0] = {status: this.playerBoard[boardI].cardStatus, duration}
         } else if(this.playerBoard[boardI].cardStatus=="Vitality"){
                    if(this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1].duration && this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration + this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1].duration}   
                    this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1] = {status: this.playerBoard[boardI].cardStatus, duration}
         } else if(this.playerBoard[boardI].cardStatus=="Shield"){this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[2] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
           else if(this.playerBoard[boardI].cardStatus=="Freeze"){this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[3] = {status: this.playerBoard[boardI].cardStatus, duration: 999}}
           if(this.playerBoard[boardI].cardStatusDuration){duration = this.playerBoard[boardI].cardStatusDuration}
           }
          }}
          if(this.playerBoard[boardI].cardEffect2=="Status" && this.playerBoard[boardI].cardEffectTarget2!="Manual"){
              let duration = 0
              if(this.playerBoard[boardI].cardStatusDuration){duration = this.playerBoard[boardI].cardStatusDuration2}
              if(this.playerBoard[boardI].cardEffectTarget2=="Self"){
                if(this.playerBoard[boardI].cardStatus2=="Bleeding"){
                    if(this.playerBoard[boardI].statusses[0].duration && this.playerBoard[boardI].statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + this.playerBoard[boardI].statusses[0].duration}   
                    this.playerBoard[boardI].statusses[0] = {status: this.playerBoard[boardI].cardStatus2, duration}
         } else if(this.playerBoard[boardI].cardStatus2=="Vitality"){
                    if(this.playerBoard[boardI].statusses[1].duration && this.playerBoard[boardI].statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + this.playerBoard[boardI].statusses[1].duration}   
                    this.playerBoard[boardI].statusses[1] = {status: this.playerBoard[boardI].cardStatus2, duration}
         } else if(this.playerBoard[boardI].cardStatus2=="Shield"){this.playerBoard[boardI].statusses[2] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
           else if(this.playerBoard[boardI].cardStatus2=="Freeze"){this.playerBoard[boardI].statusses[3] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
       } else if(this.playerBoard[boardI].cardEffectTarget2=="Left"){
                if(boardI!=0){if(this.playerBoard[boardI-1].cardName){
                  if(this.playerBoard[boardI].cardStatus2=="Bleeding"){
                    if(this.playerBoard[boardI-1].statusses[0].duration && this.playerBoard[boardI-1].statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + this.playerBoard[boardI-1].statusses[0].duration}   
                    this.playerBoard[boardI-1].statusses[0] = {status: this.playerBoard[boardI].cardStatus2, duration}
           } else if(this.playerBoard[boardI].cardStatus2=="Vitality"){
                    if(this.playerBoard[boardI-1].statusses[1].duration && this.playerBoard[boardI-1].statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + this.playerBoard[boardI-1].statusses[1].duration}   
                    this.playerBoard[boardI-1].statusses[1] = {status: this.playerBoard[boardI].cardStatus2, duration}
           } else if(this.playerBoard[boardI].cardStatus2=="Shield"){this.playerBoard[boardI-1].statusses[2] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
             else if(this.playerBoard[boardI].cardStatus2=="Freeze"){this.playerBoard[boardI-1].statusses[3] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
                }}
       } else if(this.playerBoard[boardI].cardEffectTarget2=="Right"){
                  if(boardI!=9){if(this.playerBoard[boardI+1].cardName){
                    if(this.playerBoard[boardI].cardStatus2=="Bleeding"){
                    if(this.playerBoard[boardI+1].statusses[0].duration && this.playerBoard[boardI+1].statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + this.playerBoard[boardI+1].statusses[0].duration}   
                    this.playerBoard[boardI+1].statusses[0] = {status: this.playerBoard[boardI].cardStatus2, duration}
             } else if(this.playerBoard[boardI].cardStatus2=="Vitality"){
                    if(this.playerBoard[boardI+1].statusses[1].duration && this.playerBoard[boardI+1].statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + this.playerBoard[boardI+1].statusses[1].duration}   
                    this.playerBoard[boardI+1].statusses[1] = {status: this.playerBoard[boardI].cardStatus2, duration}
             } else if(this.playerBoard[boardI].cardStatus2=="Shield"){this.playerBoard[boardI + 1].statusses[2] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
               else if(this.playerBoard[boardI].cardStatus2=="Freeze"){this.playerBoard[boardI + 1].statusses[3] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
                }}
       } else if(this.playerBoard[boardI].cardEffectTarget2=="Adjacent"){
                 if(boardI!=0){if(this.playerBoard[boardI-1].cardName){
                   if(this.playerBoard[boardI].cardStatus2=="Bleeding"){
                    if(this.playerBoard[boardI-1].statusses[0].duration && this.playerBoard[boardI-1].statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + this.playerBoard[boardI-1].statusses[0].duration}   
                    this.playerBoard[boardI-1].statusses[0] = {status: this.playerBoard[boardI].cardStatus2, duration}
            } else if(this.playerBoard[boardI].cardStatus2=="Vitality"){
                    if(this.playerBoard[boardI-1].statusses[1].duration && this.playerBoard[boardI-1].statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + this.playerBoard[boardI-1].statusses[1].duration}   
                    this.playerBoard[boardI-1].statusses[1] = {status: this.playerBoard[boardI].cardStatus2, duration}
            } else if(this.playerBoard[boardI].cardStatus2=="Shield"){this.playerBoard[boardI - 1].statusses[2] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
              else if(this.playerBoard[boardI].cardStatus2=="Freeze"){this.playerBoard[boardI - 1].statusses[3] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
                }}
                 if(boardI!=9){if(this.playerBoard[boardI+1].cardName){
                   if(this.playerBoard[boardI].cardStatus2=="Bleeding"){
                    if(this.playerBoard[boardI+1].statusses[0].duration && this.playerBoard[boardI+1].statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + this.playerBoard[boardI+1].statusses[0].duration}   
                    this.playerBoard[boardI+1].statusses[0] = {status: this.playerBoard[boardI].cardStatus2, duration}
            } else if(this.playerBoard[boardI].cardStatus2=="Vitality"){
                    if(this.playerBoard[boardI+1].statusses[1].duration && this.playerBoard[boardI+1].statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + this.playerBoard[boardI+1].statusses[1].duration}   
                    this.playerBoard[boardI+1].statusses[1] = {status: this.playerBoard[boardI].cardStatus2, duration}
            } else if(this.playerBoard[boardI].cardStatus2=="Shield"){this.playerBoard[boardI + 1].statusses[2] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
              else if(this.playerBoard[boardI].cardStatus2=="Freeze"){this.playerBoard[boardI + 1].statusses[3] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
                }}
       } else if(this.playerBoard[boardI].cardEffectTarget2=="Random"){
                  if(this.playerBoard[boardI].cardTargetUnitType2=="Ally"){
                      if(this.filledBoardSpace.length>0){
                          let unit = this.playerBoard[this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]]
                          if(this.playerBoard[boardI].cardStatus2=="Bleeding"){
                    if(unit.statusses[0].duration && unit.statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + unit.statusses[0].duration}   
                    unit.statusses[0] = {status: this.playerBoard[boardI].cardStatus2, duration}
                   } else if(this.playerBoard[boardI].cardStatus2=="Vitality"){
                    if(unit.statusses[1].duration && unit.statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + unit.statusses[1].duration}   
                    unit.statusses[1] = {status: this.playerBoard[boardI].cardStatus2, duration}
                   } else if(this.playerBoard[boardI].cardStatus2=="Shield"){unit.statusses[2] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
                     else if(this.playerBoard[boardI].cardStatus2=="Freeze"){unit.statusses[3] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
                        }
           } else if(this.playerBoard[boardI].cardTargetUnitType2=="Enemy") {
                      if(this.filledOpponentBoardSpace.length>0){
                          let unit = this.opponentBoard[this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]]
                          if(this.playerBoard[boardI].cardStatus2=="Bleeding"){
                    if(unit.statusses[0].duration && unit.statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + unit.statusses[0].duration}   
                    unit.statusses[0] = {status: this.playerBoard[boardI].cardStatus2, duration}
                   } else if(this.playerBoard[boardI].cardStatus2=="Vitality"){
                    if(unit.statusses[1].duration && unit.statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + unit.statusses[1].duration}   
                    unit.statusses[1] = {status: this.playerBoard[boardI].cardStatus2, duration}
                   } else if(this.playerBoard[boardI].cardStatus2=="Shield"){unit.statusses[2] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
                     else if(this.playerBoard[boardI].cardStatus2=="Freeze"){unit.statusses[3] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
                        }
           } else if(this.playerBoard[boardI].cardTargetUnitType2=="All"){
                    let side = Math.floor(Math.random() * 2)
                    let unit
                    if(side == 0){
                          unit = this.playerBoard[this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]]
             } else if(side == 1){
                          unit = this.opponentBoard[this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]]
             }      if(this.playerBoard[boardI].cardStatus2=="Bleeding"){
                    if(unit.statusses[0].duration && unit.statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + unit.statusses[0].duration}   
                    unit.statusses[0] = {status: this.playerBoard[boardI].cardStatus2, duration}
             } else if(this.playerBoard[boardI].cardStatus2=="Vitality"){
                    if(unit.statusses[1].duration && unit.statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + unit.statusses[1].duration}   
                    unit.statusses[1] = {status: this.playerBoard[boardI].cardStatus2, duration}
             } else if(this.playerBoard[boardI].cardStatus2=="Shield"){unit.statusses[2] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
               else if(this.playerBoard[boardI].cardStatus2=="Freeze"){unit.statusses[3] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
           }
       } else if(this.playerBoard[boardI].cardEffectTarget2=="All Allies"){
           for(let i = 0; i < this.filledBoardSpace.length; i++){
                 if(this.playerBoard[boardI].cardStatus2=="Bleeding"){
                    if(this.playerBoard[this.filledBoardSpace[i]].statusses[0].duration && this.playerBoard[this.filledBoardSpace[i]].statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + this.playerBoard[this.filledBoardSpace[i]].statusses[0].duration}   
                    this.playerBoard[this.filledBoardSpace[i]].statusses[0] = {status: this.playerBoard[boardI].cardStatus2, duration}
          } else if(this.playerBoard[boardI].cardStatus2=="Vitality"){
                    if(this.playerBoard[this.filledBoardSpace[i]].statusses[1].duration && this.playerBoard[this.filledBoardSpace[i]].statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + this.playerBoard[this.filledBoardSpace[i]].statusses[1].duration}   
                    this.playerBoard[this.filledBoardSpace[i]].statusses[1] = {status: this.playerBoard[boardI].cardStatus2, duration}
          } else if(this.playerBoard[boardI].cardStatus2=="Shield"){this.playerBoard[this.filledBoardSpace[i]].statusses[2] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
            else if(this.playerBoard[boardI].cardStatus2=="Freeze"){this.playerBoard[this.filledBoardSpace[i]].statusses[3] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
            if(this.playerBoard[boardI].cardStatusDuration2){duration = this.playerBoard[boardI].cardStatusDuration2}
           }
       } else if(this.playerBoard[boardI].cardEffectTarget2=="All Enemies"){
           for(let i = 0; i < this.filledOpponentBoardSpace.length; i++){
                if(this.playerBoard[boardI].cardStatus2=="Bleeding"){
                    if(this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0].duration && this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0].duration}   
                    this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0] = {status: this.playerBoard[boardI].cardStatus2, duration}
         } else if(this.playerBoard[boardI].cardStatus2=="Vitality"){
                    if(this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1].duration && this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1].duration>0){
                        duration = this.playerBoard[boardI].cardStatusDuration2 + this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1].duration}   
                    this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1] = {status: this.playerBoard[boardI].cardStatus2, duration}
         } else if(this.playerBoard[boardI].cardStatus2=="Shield"){this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[2] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
           else if(this.playerBoard[boardI].cardStatus2=="Freeze"){this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[3] = {status: this.playerBoard[boardI].cardStatus2, duration: 999}}
           if(this.playerBoard[boardI].cardStatusDuration2){duration = this.playerBoard[boardI].cardStatusDuration2}
           }
          }}
          if(this.playerBoard[boardI].cardEffect=="Reveal" && this.opponentHand.length>0){
              if(this.playerBoard[boardI].cardEffectTarget=="Random"){
                  let hiddenCardIndex = []
                  let opponentHandCardsI = []
                  for(let o = 0; o < 10; o++){
                      if(this.opponentHand[o].cardName){opponentHandCardsI.push(o)}
                  }
                  for(let i = 0; i < opponentHandCardsI.length; i++){
                      if(this.opponentHand[opponentHandCardsI[i]].cardName){
                          if(this.opponentHand[opponentHandCardsI[i]].revealed==false){
                              hiddenCardIndex.push(opponentHandCardsI[i])
                          }
                      }
                  }
                for(let i = 0; i < this.playerBoard[boardI].cardEffectValue; i++){
                    if(hiddenCardIndex.length>0){
                        let revealCardI = hiddenCardIndex[Math.floor(Math.random() * hiddenCardIndex.length)]
                        this.opponentHand[revealCardI].revealed=true
                        hiddenCardIndex.splice(hiddenCardIndex.indexOf(revealCardI), 1)
                    }
              } hiddenCardIndex=[]}
          }
          if(this.playerBoard[boardI].cardEffect=="Engine" || this.playerBoard[boardI].cardEffect2=="Engine"){
              if(this.playerBoard[boardI].cardEngineCondition=="Allied Unit Damaged" && this.chiefI!=null){this.chiefI2=boardI}
              else if(this.playerBoard[boardI].cardEngineCondition=="Allied Unit Damaged"){this.chiefI=boardI}
              if(this.playerBoard[boardI].cardEngineCondition=="Enemy Boosted" && this.spyI!=null){this.spyI2=boardI}
              else if(this.playerBoard[boardI].cardEngineCondition=="Enemy Boosted"){this.spyI=boardI}
              this.alliedEngines.push([this.playerBoard[boardI], boardI])
          }
          if(this.playerBoard[boardI].cardEffect=="Grave Consume" && this.playerGraveyard.length>0){
              this.showPlayerGraveyard=true
              this.consumedUnitType=this.playerBoard[boardI].consumeType
          }
          if(this.playerBoard[boardI].cardEffect=="Copy Grave Unit" && this.playerGraveyard.length>0){
              this.showPlayerGraveyard=true
          }
          if(this.playerBoard[boardI].cardEffect=="Play Card"){
              if(this.playerBoard[boardI].playedCard=="Enemy Top Deck"){
                  this.chosenPlayableCard = this.opponentDeck.shift()
                  this.showTutoredCard = true
                  if(this.opponentDeck.length){return "aaa"}
       } else if(this.playerBoard[boardI].playedCard=="Any Card From Own Deck"){
                  this.showDeck=true
                  if(this.playerDeck.length){return "aaa"}
       }
          }
          if(this.playerBoard[boardI].cardEffect=="Set Health"){
              if(this.playerBoard[boardI].cardEffectTarget=="All Units"){
                  for(let i = 0; i < this.filledBoardSpace.length; i++){
                      if(this.filledBoardSpace[i] != boardI){this.playerBoard[this.filledBoardSpace[i]].cardHealth = this.playerBoard[boardI].cardEffectValue}
                  }
                  for(let o = 0; o < this.filledOpponentBoardSpace.length; o++){
                      this.opponentBoard[this.filledOpponentBoardSpace[o]].cardHealth = this.playerBoard[boardI].cardEffectValue
                  }
              }
          }
          if(this.playerBoard[boardI].cardEffectTarget == "Manual"){
              let pass = true
              if(this.playerBoard[boardI].cardTargetUnitType=="Ally" && this.filledBoardSpace.length<2){pass = false}
              if(this.playerBoard[boardI].cardTargetUnitType=="Enemy" && this.filledOpponentBoardSpace.length==0){pass = false}
              let areRevealedCards = false
              for (let i = 0; i < this.opponentHand.length; i++){
                  if(this.opponentHand[i].revealed){areRevealedCards=true}
              }
              if(this.playerBoard[boardI].playedCard=="Revealed Card In Opponent Hand" && areRevealedCards == false){pass = false}
              if(pass==false){
                  this.chosenCardHealth = null
                  this.chosenCardEffect = ""
                  this.chosenCardTarget = ""
                  this.chosenCardTargetType = ""
                  this.chosenCardEffectValue = null
                  this.chosenCardStatus = ""
                  this.chosenCardStatusDuration = null
                  this.chosenCardEngineEffect = ""
                  this.chosenCardPlayedCard = ""
                  this.chosenCardTargetType = ""
                  this.countPoints();
                  this.cardPlayed = true
                  this.checkDeath();
              }
          }
          if(this.playerBoard[boardI].cardEffectTarget != "Manual"){
              this.countPoints();
              this.cardPlayed = true
              this.checkDeath();
          }
          if(this.playerBoard[boardI].cardEffect=="Removal"){
              let pass = false
              if(this.chosenCardRemovalCondition=="Above Value"){
                  for(let i = 0; i < this.filledOpponentBoardSpace.length; i++){
                    if(this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth>this.chosenCardRemovalConditionValue){pass=true}
              }}
              if(this.chosenCardRemovalCondition=="Bleeding Enemy Health"){
                  for(let i = 0; i < this.filledOpponentBoardSpace.length; i++){
                    if(this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0].duration>0){pass=true}
              }
              }
              if(pass==false){
                  this.chosenCardHealth = null
                  this.chosenCardEffect = ""
                  this.chosenCardTarget = ""
                  this.chosenCardTargetType = ""
                  this.chosenCardEffectValue = null
                  this.chosenCardStatus = ""
                  this.chosenCardStatusDuration = null
                  this.chosenCardEngineEffect = ""
                  this.chosenCardPlayedCard = ""
                  this.chosenCardTargetType = ""
                  this.countPoints();
                  this.cardPlayed = true
                  this.checkDeath();
              }
          }
          this.playerPlayed = true;
      },
      processDeploy(i){
          if(this.chosenCardEffectCondition=="Right Unit Health"){
              if(this.chosenCardIndex!=9){if(this.playerBoard[this.chosenCardIndex + 1].cardName){this.chosenCardEffectValue=this.playerBoard[this.chosenCardIndex + 1].cardHealth}}
          }
          if(this.chosenCardEffectCondition=="Twice The Number Of Cards In Deck"){
            this.chosenCardEffectValue = this.playerDeck.length * 2
          }
          if(this.chosenCardEffect=="Grave Consume"){
              if(this.consumedUnitType=="Bronze"){
                  if(this.playerGraveyard[i].cardRarity=="Bronze"){
                      this.playerBoard[this.filledBoardSpace[this.filledBoardSpace.length-1]].cardHealth += this.playerGraveyard[i].cardBaseHealth
                      if(this.oppSpyI!=null) {this.opponentBoard[this.oppSpyI].cardHealth += this.playerGraveyard[i].cardHealth}
                      if(this.oppSpyI2!=null) {this.opponentBoard[this.oppSpyI2].cardHealth += this.playerGraveyard[i].cardHealth}
                      this.playerGraveyard.splice(i, 1)
                      this.showPlayerGraveyard=false
                  }
              } else {
                this.playerBoard[this.filledBoardSpace[this.filledBoardSpace.length-1]].cardHealth += this.playerGraveyard[i].cardHealth
                if(this.oppSpyI!=null) {this.opponentBoard[this.oppSpyI].cardHealth += this.playerGraveyard[i].cardHealth}
                if(this.oppSpyI2!=null) {this.opponentBoard[this.oppSpyI2].cardHealth += this.playerGraveyard[i].cardHealth}
                this.playerGraveyard.splice(i, 1)
                this.showPlayerGraveyard=false
                }
          }
          if(this.chosenCardEffect=="Copy Grave Unit"){
              if(this.playerGraveyard[i].cardEffect=="Engine"){
                if(this.playerGraveyard[i].cardEngineCondition=="Allied Unit Damaged" && this.chiefI!=null){this.chiefI2=this.chosenCardIndex}
           else if(this.playerGraveyard[i].cardEngineCondition=="Allied Unit Damaged"){this.chiefI=this.chosenCardIndex}
                if(this.playerGraveyard[i].cardEngineCondition=="Enemy Boosted" && this.spyI!=null){this.spyI2=this.chosenCardIndex}
           else if(this.playerGraveyard[i].cardEngineCondition=="Enemy Boosted"){this.spyI=this.chosenCardIndex}
                this.alliedEngines.push([this.playerGraveyard[i], this.chosenCardIndex])
              }
              this.playerBoard[this.chosenCardIndex] = this.playerGraveyard[i]
              this.playerBoard[this.chosenCardIndex].cardHealth = this.playerBoard[this.chosenCardIndex].cardBaseHealth
              this.showPlayerGraveyard = false
          }
                 if(this.chosenCardTargetType=="Ally" && this.filledBoardSpace.length){
              if(this.chosenCardEffect=="Boost"){
                  this.playerBoard[i].cardHealth += this.chosenCardEffectValue
                  if(this.oppSpyI!=null) {this.opponentBoard[this.oppSpyI].cardHealth += this.chosenCardEffectValue}
                  if(this.oppSpyI2!=null) {this.opponentBoard[this.oppSpyI2].cardHealth += this.chosenCardEffectValue}
                  if(this.playerBoard[i].cardEngineCondition){if(this.playerBoard[i].cardEngineCondition=="Received Boost"){this.playerBoard[i].cardEngineValue++}}
            } if(this.chosenCardEffect=="Damage"){
                    if(this.playerBoard[i].damageBondI){
                        if(i!=9){if(this.playerBoard[i+1].cardEffect!="Unkillable"){this.playerBoard[this.playerBoard[this.playerBoard[i]].damageBondI].cardHealth -= this.chosenCardEffectValue}}
                        else{this.playerBoard[this.playerBoard[this.playerBoard[i]].damageBondI].cardHealth -= this.chosenCardEffectValue}
                        if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                        if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}
                  } else if(this.playerBoard[i].statusses[2].status=="Shield"){
                      this.playerBoard[i].statusses[2]={}
                  } else {
                      this.playerBoard[i].cardHealth -= this.chosenCardEffectValue
                      if(this.playerBoard[i].cardEngineCondition=="Damage Taken"){this.playerBoard[i].cardEngineValue++}
                    }
            } if(this.chosenCardEffect=="Status"){
                let duration = 0
                if(this.chosenCardStatusDuration){duration = this.chosenCardStatusDuration}
                  if(this.chosenCardStatus=="Bleeding") {
                      if(this.playerBoard[i].statusses[0].duration && this.playerBoard[i].statusses[0].duration>0){
                        duration = this.chosenCardStatusDuration + this.playerBoard[i].statusses[0].duration}   
                      this.playerBoard[i].statusses[0] = {status: this.chosenCardStatus, duration}
                } if(this.chosenCardStatus=="Adjacent Bleeding") {
                          if(this.playerBoard[i].statusses[0].duration && this.playerBoard[i].statusses[0].duration>0){
                            duration = this.chosenCardStatusDuration + this.playerBoard[i].statusses[0].duration}   
                          this.playerBoard[i].statusses[0] = {status: "Bleeding", duration}
                          if(this.chosenCardStatusDuration){duration = this.chosenCardStatusDuration}
                        if(i!=0){if(this.playerBoard[i-1].cardName) {
                          if(this.playerBoard[i-1].statusses[0].duration && this.playerBoard[i-1].statusses[0].duration>0){
                            duration = this.chosenCardStatusDuration + this.playerBoard[i-1].statusses[0].duration}   
                          this.playerBoard[i-1].statusses[0] = {status: "Bleeding", duration}
                          if(this.chosenCardStatusDuration){duration = this.chosenCardStatusDuration}
                      }} if(i!=9){if(this.playerBoard[i+1].cardName) {
                          if(this.playerBoard[i+1].statusses[0].duration && this.playerBoard[i+1].statusses[0].duration>0){
                            duration = this.chosenCardStatusDuration + this.playerBoard[i+1].statusses[0].duration}   
                          this.playerBoard[i+1].statusses[0] = {status: "Bleeding", duration}
                          if(this.chosenCardStatusDuration){duration = this.chosenCardStatusDuration}
                  }}
                } if(this.chosenCardStatus=="Vitality"){
                    if(this.playerBoard[i].statusses[1].duration && this.playerBoard[i].statusses[1].duration>0){
                        duration = this.chosenCardStatusDuration + this.playerBoard[i].statusses[1].duration}   
                    this.playerBoard[i].statusses[1] = {status: this.chosenCardStatus, duration}
                } if(this.chosenCardStatus=="Shield"){this.playerBoard[i].statusses[2] = {status: this.chosenCardStatus, duration: 999}}
                  if(this.chosenCardStatus=="Freeze"){this.playerBoard[i].statusses[3] = {status: this.chosenCardStatus, duration: 999}}
            } if(this.chosenCardEffect=="Damage Bond"){
                this.playerBoard[i].damageBondI = this.chosenCardIndex
            } if(this.chosenCardEffect=="Consume"){
                this.playerBoard[this.filledBoardSpace[this.filledBoardSpace.length-1]].cardHealth += this.playerBoard[i].cardHealth
                if(this.oppSpyI!=null) {this.opponentBoard[this.oppSpyI].cardHealth += this.playerBoard[i].cardHealth}
                if(this.oppSpyI2!=null) {this.opponentBoard[this.oppSpyI2].cardHealth += this.playerBoard[i].cardHealth}
                this.playerBoard[i].cardHealth=0
            }
          } else if(this.chosenCardTargetType=="Enemy" && this.filledOpponentBoardSpace.length){
              if(this.chosenCardEffect=="Boost"){
                  this.opponentBoard[i].cardHealth += this.chosenCardEffectValue
                  if(this.spyI!=null){this.playerBoard[this.spyI].cardHealth += this.chosenCardEffectValue}
                  if(this.spyI2!=null){this.playerBoard[this.spyI2].cardHealth += this.chosenCardEffectValue}
                  if(this.opponentBoard[i].cardEngineCondition){if(this.opponentBoard[i].cardEngineCondition=="Received Boost"){this.opponentBoard[i].cardEngineValue++}}
       } else if(this.chosenCardEffect=="Damage"){
                    if(this.opponentBoard[i].damageBondI){
                        this.opponentBoard[this.opponentBoard[this.opponentBoard[i]].damageBondI].cardHealth -= this.chosenCardEffectValue
                  } else if(this.opponentBoard[i].statusses[2].status=="Shield"){
                      this.opponentBoard[i].statusses[2]={}
                  } else {
                      if(i!=9){if(this.opponentBoard[i+1].cardEffect!="Unkillable"){this.opponentBoard[i].cardHealth -= this.chosenCardEffectValue}}
                      else{this.opponentBoard[i].cardHealth -= this.chosenCardEffectValue}
                      if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                      if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                      if(this.opponentBoard[i].cardEngineCondition){if(this.opponentBoard[i].cardEngineCondition=="Damage Taken"){this.opponentBoard[i].cardEngineValue++}}
                  }
       } else if(this.chosenCardEffect=="Adjacent Damage"){
                    if(this.opponentBoard[i].damageBondI){
                        this.opponentBoard[this.opponentBoard[this.opponentBoard[i]].damageBondI].cardHealth -= this.chosenCardEffectValue
                  } else if(this.opponentBoard[i].statusses[2].status=="Shield"){
                      this.opponentBoard[i].statusses[2]={}
                  } else {
                      if(this.opponentBoard[i+1].cardEffect!="Unkillable"){this.opponentBoard[i].cardHealth -= this.chosenCardEffectValue}
                      if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                      if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                      if(this.OpponentBoard[i].cardEngineCondition=="Damage Taken"){this.opponentBoard[i].cardEngineValue++}
                  }
                if(i!=0){if(this.opponentBoard[i-1].cardName){
                      if(this.opponentBoard[i-1].damageBondI){
                        this.opponentBoard[this.opponentBoard[this.opponentBoard[i-1]].damageBondI].cardHealth -= this.chosenCardEffectValue
                  } else if(this.opponentBoard[i-1].statusses[2].status=="Shield"){
                      this.opponentBoard[i-1].statusses[2]={}
                  } else {
                      if(this.opponentBoard[i].cardEffect!="Unkillable"){this.opponentBoard[i-1].cardHealth -= this.chosenCardEffectValue}
                      if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                      if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                      if(this.OpponentBoard[i-1].cardEngineCondition=="Damage Taken"){this.opponentBoard[i-1].cardEngineValue++}
                  }
                }}
                if(i!=9){if(this.opponentBoard[i+1].cardName){
                      if(this.opponentBoard[i+1].damageBondI){
                        this.opponentBoard[this.opponentBoard[this.opponentBoard[i+1]].damageBondI].cardHealth -= this.chosenCardEffectValue
                  } else if(this.opponentBoard[i+1].statusses[2].status=="Shield"){
                      this.opponentBoard[i+1].statusses[2]={}
                  } else {
                      if(this.opponentBoard[i+2].cardEffect!="Unkillable"){this.opponentBoard[i+1].cardHealth -= this.chosenCardEffectValue}
                      if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                      if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                      if(this.OpponentBoard[i+1].cardEngineCondition=="Damage Taken"){this.opponentBoard[i+1].cardEngineValue++}
                  }
                }}
       } else if(this.chosenCardEffect=="Status"){
                let duration = 0
                if(this.chosenCardStatusDuration){duration = this.chosenCardStatusDuration}
                  if(this.chosenCardStatus=="Bleeding") {
                      if(this.opponentBoard[i].statusses[0].duration && this.opponentBoard[i].statusses[0].duration>0){
                        duration = this.chosenCardStatusDuration + this.opponentBoard[i].statusses[0].duration}   
                      this.opponentBoard[i].statusses[0] = {status: this.chosenCardStatus, duration}
                      if(this.chosenCardStatusDuration){duration = this.chosenCardStatusDuration}
                } if(this.chosenCardStatus=="Adjacent Bleeding") {
                      if(this.opponentBoard[i].statusses[0].duration && this.opponentBoard[i].statusses[0].duration>0){
                        duration = this.chosenCardStatusDuration + this.opponentBoard[i].statusses[0].duration}   
                      this.opponentBoard[i].statusses[0] = {status: "Bleeding", duration}
                      if(this.chosenCardStatusDuration){duration = this.chosenCardStatusDuration}
                      if(i!=0){if(this.opponentBoard[i-1].cardName) {
                        if(this.opponentBoard[i-1].statusses[0].duration && this.opponentBoard[i-1].statusses[0].duration>0){
                          duration = this.chosenCardStatusDuration + this.opponentBoard[i-1].statusses[0].duration}   
                        this.opponentBoard[i-1].statusses[0] = {status: "Bleeding", duration}
                        if(this.chosenCardStatusDuration){duration = this.chosenCardStatusDuration}
                    }} if(i!=9){if(this.opponentBoard[i+1].cardName) {
                        if(this.opponentBoard[i+1].statusses[0].duration && this.opponentBoard[i+1].statusses[0].duration>0){
                          duration = this.chosenCardStatusDuration + this.opponentBoard[i+1].statusses[0].duration}   
                        this.opponentBoard[i+1].statusses[0] = {status: "Bleeding", duration}
                        if(this.chosenCardStatusDuration){duration = this.chosenCardStatusDuration}
                    }}
                } if(this.chosenCardStatus=="Vitality"){
                    if(this.opponentBoard[i].statusses[1].duration && this.opponentBoard[i].statusses[1].duration>0){
                        duration = this.chosenCardStatusDuration + this.opponentBoard[i].statusses[1].duration}   
                    this.opponentBoard[i].statusses[1] = {status: this.chosenCardStatus, duration}
                } if(this.chosenCardStatus=="Shield"){this.opponentBoard[i].statusses[2] = {status: this.chosenCardStatus, duration: 999}}
                  if(this.chosenCardStatus=="Freeze"){this.opponentBoard[i].statusses[3] = {status: this.chosenCardStatus, duration: 999}}
       } else if(this.chosenCardEffect=="Trade Place"){
        if(this.opponentBoard[i].cardEffect=="Engine" || this.opponentBoard[i].cardEffect2=="Engine"){
           if(this.oppChiefI==i){this.oppChiefI=null}
       else if(this.oppChiefI2==i){this.oppChiefI2=null}
           if(this.oppSpyI==i){this.oppSpyI=null}
       else if(this.oppSpyI2==i){this.oppSpyI2=null}
           if(this.opponentBoard[i].cardEngineCondition=="Allied Unit Damaged" && this.chiefI!=null){this.chiefI2=this.chosenCardIndex}
      else if(this.opponentBoard[i].cardEngineCondition=="Allied Unit Damaged"){this.chiefI=this.chosenCardIndex}
           if(this.opponentBoard[i].cardEngineCondition=="Enemy Boosted" && this.spyI!=null){this.spyI2=this.chosenCardIndex}
      else if(this.opponentBoard[i].cardEngineCondition=="Enemy Boosted"){this.spyI=this.chosenCardIndex}
           for(let o = 0; o < this.opponentEngines.length; o++){
               if(this.opponentEngines[o][1]==i){
                   let engine = this.opponentEngines.splice(o, 1);
                   console.log(`Engine: ${engine}`)
                   this.alliedEngines.push(engine)}
           }
       }
           let playerTrade = this.playerBoard[this.chosenCardIndex]
           let opponentTrade = this.opponentBoard[i]
           this.playerBoard[this.chosenCardIndex] = opponentTrade
           this.opponentBoard[i] = playerTrade
       } else if(this.chosenCardEffect=="Removal"){
                if(this.chosenCardRemovalCondition){
                    if(this.chosenCardRemovalCondition=="Above Value"){
                        let pass = false
                        for(let o = 0; o < this.opponentBoard.length; o++){
                            if(this.opponentBoard[o].cardHealth>this.chosenCardRemovalConditionValue){pass=true}
                        }
                        if(pass){
                        if(this.opponentBoard[i].cardHealth>this.chosenCardRemovalConditionValue){this.opponentBoard[i].cardHealth=0}
                        else {return}
                    }} else if(this.chosenCardRemovalCondition=="Bleeding Enemy Health"){
                        if(this.opponentBoard[i].statusses[0].duration>0){
                            this.playerBoard[this.chosenCardIndex].cardHealth += this.opponentBoard[i].cardHealth
                            this.opponentBoard[i].cardHealth=0}
                        else {return}
                    }
                }
            }
            }
                this.chosenCardHealth = null
                this.chosenCardEffect = ""
                this.chosenCardTarget = ""
                this.chosenCardTargetType = ""
                this.chosenCardEffectValue = null
                this.chosenCardStatus = ""
                this.chosenCardStatusDuration = null
                this.chosenCardEngineEffect = ""
                this.chosenCardTargetType = ""
                this.cardPlayed = true
                this.checkDeath();
                this.countPoints();
      },
      startEnemyTurn(){
          if(!this.opponentPassed){this.isEnemyTurn=true}
          this.playerPlayed = true;
          console.log("Enemy turn started")
          this.countPoints();
          this.processEngines();
          this.processStatus();
          this.checkDeath();
          setTimeout(() => {
            if(!this.opponentPassed){this.isEnemyTurn=true}
            this.playerPlayed = true;
            if(this.playerPlayed && this.isEnemyTurn){this.playEnemyCard(); this.isEnemyTurn=false}
            else{this.playerPlayed=false}
            this.checkDeath();
            this.processEnemyEngines();
            this.processEnemyStatus();
            this.checkDeath();
            this.countPoints();
            if(!this.playerPassed){
              this.isEnemyTurn = false
              this.playerPlayed = false;
            }
            this.checkRoundEnd();
        }, 2000)
      },
      playEnemyCard(){
          console.log("Enemy plays card")
          let handI = []
          for(let i = 0; i<10; i++){
                if(this.opponentHand[i].cardName!=undefined){handI.push(i)}
          }
          let availableSpace=[]
          for(let i = 0; i<10; i++){
            if(this.filledOpponentBoardSpace.indexOf(i)==-1){
                availableSpace.push(i)
            }
          }
          let boardI = null
          let noSpace = false 
          let shouldPass = false
          if(!this.chosenEnemyPlayableCard){
            if(!this.playerWonRound && ((this.opponentScore >= this.playerScore + 10) || ((this.opponentScore + 10 <= this.playerScore)) && (handI.length<9))){shouldPass = true}
            if(availableSpace.length==0){noSpace = true; this.opponentPassed=true; this.isEnemyTurn=false; this.playerPlayed=false; return "aaa"}
            if(this.playerPassed && this.playerScore < this.opponentScore){this.opponentPassed=true; this.isEnemyTurn=true; this.playerPlayed=true; return "aaa"}
            if(handI.length==0 || shouldPass){this.opponentPassed=true; this.isEnemyTurn=true; this.playerPlayed=true; return "aaa"
            } else {this.chosenEnemyPlayableCardIndex = this.chooseEnemyCard(this.opponentHand, handI)}
            if(this.chosenEnemyPlayableCardIndex==undefined){this.chosenEnemyPlayableCardIndex=handI[Math.floor(Math.random()*handI.length)]}
            this.chosenEnemyPlayableCard = this.opponentHand[this.chosenEnemyPlayableCardIndex]
          }
        
        if(availableSpace.length!=0) {boardI = this.chooseEnemyCardPosition(availableSpace)
        } else {this.discardEnemyCard()}
        if(noSpace==false){
          this.chosenEnemyCardEffect = this.chosenEnemyPlayableCard.cardEffect
          this.chosenEnemyCardEffectCondition = this.chosenEnemyPlayableCard.cardEffectCondition
          this.chosenEnemyCardTarget = this.chosenEnemyPlayableCard.cardEffectTarget
          this.chosenEnemyCardTargetType = this.chosenEnemyPlayableCard.cardTargetUnitType
          this.chosenEnemyCardEffectValue = this.chosenEnemyPlayableCard.cardEffectValue
          this.chosenEnemyCardStatus = this.chosenEnemyPlayableCard.cardStatus
          this.chosenEnemyCardStatusDuration = this.chosenEnemyPlayableCard.cardStatusDuration
          this.chosenEnemyCardEngineEffect = this.chosenEnemyPlayableCard.cardEngineType
          this.chosenEnemyCardRemovalCondition = this.chosenEnemyPlayableCard.cardRemovalCondition
          this.chosenEnemyCardRemovalConditionValue = this.chosenEnemyPlayableCard.cardRemovalConditionValue
          this.chosenEnemyCardPlayedCard = this.chosenEnemyPlayableCard.playedCard
          this.chosenEnemyCardIndex = boardI
          this.chosenEnemyCardHealth=0
          for(let i = 0; i<this.chosenEnemyPlayableCard.cardBaseHealth; i++){this.chosenEnemyCardHealth++}
          this.opponentBoard[boardI] = {
              cardAmount: this.chosenEnemyPlayableCard.cardAmount,
              cardName: this.chosenEnemyPlayableCard.cardName,
              cardBaseHealth: this.chosenEnemyPlayableCard.cardBaseHealth,
              cardHealth: this.chosenEnemyCardHealth,
              cardEffect: this.chosenEnemyPlayableCard.cardEffect,
              cardEffectCondition: this.chosenEnemyPlayableCard.cardEffectCondition,
              cardEffectTarget: this.chosenEnemyPlayableCard.cardEffectTarget,
              cardStatus: this.chosenEnemyPlayableCard.cardStatus,
              cardStatus2: this.chosenEnemyPlayableCard.cardStatus2,
              cardStatusDuration: this.chosenEnemyPlayableCard.cardStatusDuration,
              cardStatusDuration2: this.chosenEnemyPlayableCard.cardStatusDuration,
              cardTargetUnitType: this.chosenEnemyPlayableCard.cardTargetUnitType,
              cardTargetUnitType2: this.chosenEnemyPlayableCard.cardTargetUnitType2,
              cardEffectValue: this.chosenEnemyPlayableCard.cardEffectValue,
              cardEffect2: this.chosenEnemyPlayableCard.cardEffect2,
              cardEffectTarget2: this.chosenEnemyPlayableCard.cardEffectTarget2,
              cardEffectValue2: this.chosenEnemyPlayableCard.cardEffectValue2,
              cardEngineType: this.chosenEnemyPlayableCard.cardEngineType,
              cardEngineTarget: this.chosenEnemyPlayableCard.cardEngineTarget,
              cardEngineValue: this.chosenEnemyPlayableCard.cardEngineValue,
              cardEngineCondition: this.chosenEnemyPlayableCard.cardEngineCondition,
              cardEngineType2: this.chosenEnemyPlayableCard.cardEngineType2,
              cardEngineTarget2: this.chosenEnemyPlayableCard.cardEngineTarget2,
              cardEngineValue2: this.chosenEnemyPlayableCard.cardEngineValue2,
              cardEngineCondition2: this.chosenEnemyPlayableCard.cardEngineCondition2,
              cardRandomness1: this.chosenEnemyPlayableCard.cardRandomness1,
              cardRandomness2: this.chosenEnemyPlayableCard.cardRandomness2,
              cardRemovalCondition: this.chosenEnemyPlayableCard.cardRemovalCondition,
              cardRemovalConditionValue: this.chosenEnemyPlayableCard.cardRemovalConditionValue,
              playedCard: this.chosenEnemyPlayableCard.playedCard,
              consumeType: this.chosenEnemyPlayableCard.consumeType,
              cardRarity: this.chosenEnemyPlayableCard.cardRarity,
              cardDescription: this.chosenEnemyPlayableCard.cardDescription,
              statusses: [{}, {}, {}, {}]
          }
          this.chosenEnemyPlayableCard.cardAmount++
          if(this.chosenEnemyPlayableCardIndex!=undefined){this.opponentHand[this.chosenEnemyPlayableCardIndex]={}}
          this.chosenEnemyCard={};
          this.chosenEnemyPlayableCard=null,
          this.showTutoredCard=false
          this.filledOpponentBoardSpace.push(boardI)
          this.checkDeath()

          if(this.opponentBoard[boardI].cardEffectTarget=="Left" && boardI==0){
              this.opponentBoard[boardI].cardEffectTarget=""
              this.opponentBoard[boardI].cardEffect=""
          }
          if(this.opponentBoard[boardI].cardEffectTarget=="Right" && boardI==9){
              this.opponentBoard[boardI].cardEffectTarget=""
              this.opponentBoard[boardI].cardEffect=""
          }
          if(this.opponentBoard[boardI].cardEffectTarget=="Adjacent" && boardI==0){
              this.opponentBoard[boardI].cardEffectTarget="Right"
          }
          if(this.opponentBoard[boardI].cardEffectTarget=="Adjacent" && boardI==9){
              this.opponentBoard[boardI].cardEffectTarget="Left"
          }
          if(this.opponentBoard[boardI].cardEngineTarget=="Left" && boardI==0){
              this.opponentBoard[boardI].cardEngineTarget=""
              this.opponentBoard[boardI].cardEffect=""
          }
          if(this.opponentBoard[boardI].cardEngineTarget=="Right" && boardI==9){
              this.opponentBoard[boardI].cardEngineTarget=""
              this.opponentBoard[boardI].cardEffect=""
          }
          if(this.opponentBoard[boardI].cardEngineTarget=="Adjacent" && boardI==0){
              this.opponentBoard[boardI].cardEngineTarget="Right"
          }
          if(this.opponentBoard[boardI].cardEngineTarget=="Adjacent" && boardI==9){
              this.opponentBoard[boardI].cardEngineTarget="Left"
          }

          if(this.opponentBoard[boardI].cardEffect!="Status" && this.opponentBoard[boardI].cardEffectTarget!="Manual"){
                if(this.opponentBoard[boardI].cardEffectCondition=="Random"){
                      let value
                      value = Math.floor(Math.random() * (this.opponentBoard[boardI].cardRandomness2 - this.opponentBoard[boardI].cardRandomness1)) + this.opponentBoard[boardI].cardRandomness1
                      this.opponentBoard[boardI].cardEffectValue = value
                }
                if(this.opponentBoard[boardI].cardEffectCondition=="Twice The Number Of Card In Hand"){
                      let value = 0
                      for(let i = 0; i<10; i++){if(this.playerHand[i].cardName){value+=2}}
                      this.opponentBoard[boardI].cardEffectValue = value
                }
              if(this.opponentBoard[boardI].cardEffectTarget=="Self"){
                  if(this.opponentBoard[boardI].cardEffect=="Damage") {
                    if(boardI!=9){if(this.opponentBoard[boardI+1].cardEffect!="Unkillable"){this.opponentBoard[boardI].cardHealth -= this.opponentBoard[boardI].cardEffectValue}}
                    else {this.opponentBoard[boardI].cardHealth -= this.opponentBoard[boardI].cardEffectValue}
                    if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                    if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                    }
             else if(this.opponentBoard[boardI].cardEffect=="Boost") {
                    this.opponentBoard[boardI].cardHealth += this.opponentBoard[boardI].cardEffectValue
                    if(this.spyI!=null){this.playerBoard[this.spyI].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                    if(this.spyI2!=null){this.playerBoard[this.spyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                    }
       } else if(this.opponentBoard[boardI].cardEffectTarget=="Left"){
           if(boardI!=0){if(this.opponentBoard[boardI-1].cardName){
                  if(this.opponentBoard[boardI].cardEffect=="Boost"){
                    this.opponentBoard[boardI-1].cardHealth += this.opponentBoard[boardI].cardEffectValue
                    if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                    if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                    if(this.opponentBoard[boardI-1].cardEngineCondition=="Received Boost"){this.opponentBoard[boardI-1].cardEngineValue++}
           } else if(this.opponentBoard[boardI].cardEffect=="Damage"){
                    if(this.opponentBoard[boardI-1].damageBondI){
                        this.opponentBoard[this.opponentBoard[this.opponentBoard[boardI-1]].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue
             } else if(this.opponentBoard[boardI-1].statusses[2].status=="Shield"){
                      this.opponentBoard[boardI-1].statusses[2]={}
                  } else {
                      this.opponentBoard[boardI-1].cardHealth -= this.opponentBoard[boardI].cardEffectValue
                      if(this.opponentBoard[boardI-1].cardEngineCondition=="Damage Taken"){this.opponentBoard[boardI-1].cardEngineValue++}
                      if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                      if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                    }}}}
       } else if(this.opponentBoard[boardI].cardEffectTarget=="Right"){
                if(boardI!=9){if(this.opponentBoard[boardI+1].cardName){
                  if(this.opponentBoard[boardI].cardEffect=="Boost"){
                    this.opponentBoard[boardI+1].cardHealth += this.opponentBoard[boardI].cardEffectValue
                    if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                    if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                    if(this.opponentBoard[boardI+1].cardEngineCondition=="Received Boost"){this.opponentBoard[boardI+1].cardEngineValue++}}
             else if(this.opponentBoard[boardI].cardEffect=="Damage"){
                    if(this.opponentBoard[boardI+1].damageBondI){
                        this.opponentBoard[this.opponentBoard[this.opponentBoard[boardI+1]].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue
             } else if(this.opponentBoard[boardI+1].statusses[2].status=="Shield"){
                      this.opponentBoard[boardI+1].statusses[2]={}
                  } else {
                      if(boardI<8){if(this.opponentBoard[boardI+2].cardEffect!="Unkillable"){this.opponentBoard[boardI+1].cardHealth -= this.opponentBoard[boardI].cardEffectValue}}
                      else{this.opponentBoard[boardI+1].cardHealth -= this.opponentBoard[boardI].cardEffectValue}
                      if(this.opponentBoard[boardI+1].cardEngineCondition=="Damage Taken"){this.opponentBoard[boardI+1].cardEngineValue++}
                      if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                      if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                }}}}
       } else if(this.opponentBoard[boardI].cardEffectTarget=="Adjacent"){
                if(boardI!=0){if(this.opponentBoard[boardI-1].cardName){
                    if(this.opponentBoard[boardI].cardEffect=="Boost"){
                        this.opponentBoard[boardI-1].cardHealth += this.opponentBoard[boardI].cardEffectValue
                        if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                        if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                        if(this.opponentBoard[boardI-1].cardEngineCondition=="Received Boost"){this.opponentBoard[boardI-1].cardEngineValue++
                        }}
                else if(this.opponentBoard[boardI].cardEffect=="Damage"){
                        if(this.opponentBoard[boardI-1].damageBondI){
                            this.opponentBoard[this.opponentBoard[this.opponentBoard[boardI-1]].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue
                } else if(this.opponentBoard[boardI-1].statusses[2].status=="Shield"){
                        this.opponentBoard[boardI-1].statusses[2]={}
                    } else {
                        this.opponentBoard[boardI-1].cardHealth -= this.opponentBoard[boardI].cardEffectValue
                        if(this.opponentBoard[boardI-1].cardEngineCondition=="Damage Taken"){this.opponentBoard[boardI-1].cardEngineValue++}
                        if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                        if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                }}}}
                if(boardI!=9){if(this.opponentBoard[boardI+1].cardName){
                    if(this.opponentBoard[boardI].cardEffect=="Boost"){
                        this.opponentBoard[boardI+1].cardHealth += this.opponentBoard[boardI].cardEffectValue
                        if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                        if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                        if(this.opponentBoard[boardI+1].cardEngineCondition=="Received Boost"){this.opponentBoard[boardI+1].cardEngineValue++
                        }}
                else if(this.opponentBoard[boardI].cardEffect=="Damage"){
                        if(this.opponentBoard[boardI+1].damageBondI){
                            this.opponentBoard[this.opponentBoard[this.opponentBoard[boardI+1]].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue
                } else if(this.opponentBoard[boardI+1].statusses[2].status=="Shield"){
                        this.opponentBoard[boardI+1].statusses[2]={}
                    } else {
                        if(boardI<8){if(this.opponentBoard[boardI+2].cardEffect!="Unkillable"){this.opponentBoard[boardI+1].cardHealth -= this.opponentBoard[boardI].cardEffectValue}}
                        else{this.opponentBoard[boardI+1].cardHealth -= this.opponentBoard[boardI].cardEffectValue}
                        if(this.opponentBoard[boardI+1].cardEngineCondition=="Damage Taken"){this.opponentBoard[boardI+1].cardEngineValue++}
                        if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                        if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                }}}}
       } else if(this.opponentBoard[boardI].cardEffectTarget=="Random"){
                  if(this.opponentBoard[boardI].cardTargetUnitType=="Ally"){
                      if(this.filledOpponentBoardSpace.length>0){
                          let unitI = this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]
                          if(this.opponentBoard[boardI].cardEffect=="Boost"){
                            this.opponentBoard[unitI].cardHealth += this.opponentBoard[boardI].cardEffectValue
                            if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                            if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                            if(this.opponentBoard[unitI].cardEngineCondition=="Received Boost"){this.opponentBoard[unitI].cardEngineValue++}}
                     else if(this.opponentBoard[boardI].cardEffect=="Damage"){
                            if(this.opponentBoard[unitI].damageBondI){
                              this.opponentBoard[this.opponentBoard[unitI].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue
                     } else if(this.opponentBoard[unitI].statusses[2].status=="Shield"){
                              this.opponentBoard[unitI].statusses[2]={}
                     } else {
                         if(unitI!=9){if(this.opponentBoard[unitI+1].cardEffect!="Unkillable"){this.opponentBoard[unitI].cardHealth -= this.opponentBoard[boardI].cardEffectValue}}
                         else{this.opponentBoard[unitI].cardHealth -= this.opponentBoard[boardI].cardEffectValue}
                         if(this.opponentBoard[unitI].cardEngineCondition=="Damage Taken"){this.opponentBoard[unitI].cardEngineValue++}
                         if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                         if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}
                        }}
           } else if(this.opponentBoard[boardI].cardTargetUnitType=="Enemy"){
                      if(this.filledBoardSpace.length>0){
                          let unitI = this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]
                          if(this.opponentBoard[boardI].cardEffect=="Boost"){
                            this.playerBoard[unitI].cardHealth += this.opponentBoard[boardI].cardEffectValue
                            if(this.oppSpyI!=null) {this.opponentBoard[this.oppSpyI].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                            if(this.oppSpyI2!=null) {this.opponentBoard[this.oppSpyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                            if(this.playerBoard[unitI].cardEngineCondition=="Received Boost"){this.playerBoard[unitI].cardEngineValue++}}
                     else if(this.opponentBoard[boardI].cardEffect=="Damage"){
                            if(this.playerBoard[unitI].damageBondI){
                              this.playerBoard[this.playerBoard[unitI].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue
                     } else if(this.playerBoard[unitI].statusses[2].status=="Shield"){
                              this.playerBoard[unitI].statusses[2]={}
                     } else {
                         if(unitI!=9){if(this.playerBoard[unitI+1].cardEffect!="Unkillable"){this.playerBoard[unitI].cardHealth -= this.opponentBoard[boardI].cardEffectValue}}
                         else{this.playerBoard[unitI].cardHealth -= this.opponentBoard[boardI].cardEffectValue}
                         if(this.playerBoard[unitI].cardEngineCondition=="Damage Taken"){this.playerBoard[unitI].cardEngineValue++}
                         if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                         if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}
                    }}
                        }
           } else if(this.opponentBoard[boardI].cardTargetUnitType=="All"){
                    let side = Math.floor(Math.random() * 2)
                    if(side == 0){
                       if(this.filledOpponentBoardSpace.length>0){
                          let unitI = this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]
                          if(this.opponentBoard[boardI].cardEffect=="Boost"){
                            this.opponentBoard[unitI].cardHealth += this.opponentBoard[boardI].cardEffectValue
                            if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                            if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                            if(this.opponentBoard[unitI].cardEngineCondition=="Received Boost"){this.opponentBoard[unitI].cardEngineValue++}}
                     else if(this.opponentBoard[boardI].cardEffect=="Damage"){
                            if(this.opponentBoard[unitI].damageBondI){
                              this.opponentBoard[this.opponentBoard[unitI].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue
                     } else if(this.opponentBoard[unitI].statusses[2].status=="Shield"){
                              this.opponentBoard[unitI].statusses[2]={}
                     } else {
                         if(unitI!=9){if(this.opponentBoard[unitI+1].cardEffect!="Unkillable"){this.opponentBoard[unitI].cardHealth -= this.opponentBoard[boardI].cardEffectValue}}
                         else{this.opponentBoard[unitI].cardHealth -= this.opponentBoard[boardI].cardEffectValue}
                         if(this.opponentBoard[unitI].cardEngineCondition=="Damage Taken"){this.opponentBoard[unitI].cardEngineValue++}
                         if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                         if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}
                        }}
             } else if(side == 1){
                      if(this.filledBoardSpace.length>0){
                          let unitI = this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]
                          if(this.opponentBoard[boardI].cardEffect=="Boost"){
                            this.playerBoard[unitI].cardHealth += this.opponentBoard[boardI].cardEffectValue
                            if(this.oppSpyI!=null) {this.opponentBoard[this.oppSpyI].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                            if(this.oppSpyI2!=null) {this.opponentBoard[this.oppSpyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                            if(this.playerBoard[unitI].cardEngineCondition=="Received Boost"){this.playerBoard[unitI].cardEngineValue++}}
                     else if(this.opponentBoard[boardI].cardEffect=="Damage"){
                            if(this.playerBoard[unitI].damageBondI){
                              this.playerBoard[this.playerBoard[unitI].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue
                     } else if(this.playerBoard[unitI].statusses[2].status=="Shield"){
                              this.playerBoard[unitI].statusses[2]={}
                     } else {
                         if(unitI!=9){if(this.playerBoard[unitI+1].cardEffect!="Unkillable"){this.playerBoard[unitI].cardHealth -= this.opponentBoard[boardI].cardEffectValue}}
                         else{this.playerBoard[unitI].cardHealth -= this.opponentBoard[boardI].cardEffectValue}
                         if(this.playerBoard[unitI].cardEngineCondition=="Damage Taken"){this.playerBoard[unitI].cardEngineValue++}
                         if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                         if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}
                    }}
                }
             }
           }
       } else if(this.opponentBoard[boardI].cardEffectTarget=="All Allies"){
           for(let i = 0; i < this.filledOpponentBoardSpace.length; i++){
               if(this.opponentBoard[boardI].cardEffect=="Boost"){
                    this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth += this.opponentBoard[boardI].cardEffectValue
                    if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                    if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                    if(this.opponentBoard[this.filledOpponentBoardSpace[i]].cardEngineCondition=="Received Boost"){this.opponentBoard[this.filledOpponentBoardSpace[i]].cardEngineValue++}}
             else if(this.opponentBoard[boardI].cardEffect=="Damage"){
                    if(this.opponentBoard[this.filledOpponentBoardSpace[i]].damageBondI){
                        this.opponentBoard[this.opponentBoard[this.opponentBoard[this.filledOpponentBoardSpace[i]]].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue
             } else if(this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[2].status=="Shield"){
                      this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[2]={}
                  } else {
                      if(this.filledOpponentBoardSpace[i]!=9){if(this.opponentBoard[this.filledOpponentBoardSpace[i]+1].cardEffect!="Unkillable"){this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth -= this.opponentBoard[boardI].cardEffectValue}}
                      else{this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth -= this.opponentBoard[boardI].cardEffectValue}
                      if(this.opponentBoard[this.filledOpponentBoardSpace[i]].cardEngineCondition=="Damage Taken"){this.opponentBoard[this.filledOpponentBoardSpace[i]].cardEngineValue++}
                      if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                      if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}}
           }
       } else if(this.opponentBoard[boardI].cardEffectTarget=="All Enemies"){
           for(let i = 0; i < this.filledBoardSpace.length; i++){
               if(this.opponentBoard[boardI].cardEffect=="Boost"){
                    this.playerBoard[this.filledBoardSpace[i]].cardHealth += this.opponentBoard[boardI].cardEffectValue
                    if(this.oppSpyI!=null) {this.opponentBoard[this.oppSpyI].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                    if(this.oppSpyI2!=null) {this.opponentBoard[this.oppSpyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue}
                    if(this.playerBoard[this.filledBoardSpace[i]].cardEngineCondition=="Received Boost"){this.playerBoard[this.filledBoardSpace[i]].cardEngineValue++}}
             else if(this.opponentBoard[boardI].cardEffect=="Damage"){
                    if(this.playerBoard[this.filledBoardSpace[i]].damageBondI){
                        this.playerBoard[this.playerBoard[this.playerBoard[this.filledBoardSpace[i]]].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue
             } else if(this.playerBoard[this.filledBoardSpace[i]].statusses[2].status=="Shield"){
                      this.playerBoard[this.filledBoardSpace[i]].statusses[2]={}
                  } else {
                      if(this.filledBoardSpace[i]!=9){if(this.playerBoard[this.filledBoardSpace[i]+1].cardEffect!="Unkillable"){this.playerBoard[this.filledBoardSpace[i]].cardHealth -= this.opponentBoard[boardI].cardEffectValue}}
                      else{this.playerBoard[this.filledBoardSpace[i]].cardHealth -= this.opponentBoard[boardI].cardEffectValue}
                      if(this.playerBoard[this.filledBoardSpace[i]].cardEngineCondition=="Damage Taken"){this.playerBoard[this.filledBoardSpace[i]].cardEngineValue++}
                      if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                      if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}
                    }}
           }
          }}
          if(this.opponentBoard[boardI].cardEffect2!="Status" && this.opponentBoard[boardI].cardEffectTarget2!="Manual"){
                if(this.opponentBoard[boardI].cardEffectCondition2=="Random"){
                      let value
                      value = Math.floor(Math.random() * (this.opponentBoard[boardI].cardRandomness2 - this.opponentBoard[boardI].cardRandomness1)) + this.opponentBoard[boardI].cardRandomness1
                      this.opponentBoard[boardI].cardEffectValue2 = value
                }
                if(this.opponentBoard[boardI].cardEffectCondition2=="Twice The Number Of Card In Hand"){
                      let value = 0
                      for(let i = 0; i<10; i++){if(this.playerHand[i].cardName){value+=2}}
                      this.opponentBoard[boardI].cardEffectValue2 = value
                }
              if(this.opponentBoard[boardI].cardEffectTarget2=="Self"){
                  if(this.opponentBoard[boardI].cardEffect2=="Damage") {
                    if(boardI!=9){if(this.opponentBoard[boardI+1].cardEffect!="Unkillable"){this.opponentBoard[boardI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2}}
                    else {this.opponentBoard[boardI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2}
                    if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                    if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                    }
             else if(this.opponentBoard[boardI].cardEffect2=="Boost") {
                    this.opponentBoard[boardI].cardHealth += this.opponentBoard[boardI].cardEffectValue2
                    if(this.spyI!=null){this.playerBoard[this.spyI].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                    if(this.spyI2!=null){this.playerBoard[this.spyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                    }
       } else if(this.opponentBoard[boardI].cardEffectTarget2=="Left"){
           if(boardI!=0){if(this.opponentBoard[boardI-1].cardName){
                  if(this.opponentBoard[boardI].cardEffect2=="Boost"){
                    this.opponentBoard[boardI-1].cardHealth += this.opponentBoard[boardI].cardEffectValue2
                    if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                    if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                    if(this.opponentBoard[boardI-1].cardEngineCondition=="Received Boost"){this.opponentBoard[boardI-1].cardEngineValue++}
           } else if(this.opponentBoard[boardI].cardEffect2=="Damage"){
                    if(this.opponentBoard[boardI-1].damageBondI){
                        this.opponentBoard[this.opponentBoard[this.opponentBoard[boardI-1]].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2
             } else if(this.opponentBoard[boardI-1].statusses[2].status=="Shield"){
                      this.opponentBoard[boardI-1].statusses[2]={}
                  } else {
                      this.opponentBoard[boardI-1].cardHealth -= this.opponentBoard[boardI].cardEffectValue2
                      if(this.opponentBoard[boardI-1].cardEngineCondition=="Damage Taken"){this.opponentBoard[boardI-1].cardEngineValue++}
                      if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                      if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                    }}}}
       } else if(this.opponentBoard[boardI].cardEffectTarget2=="Right"){
                if(boardI!=9){if(this.opponentBoard[boardI+1].cardName){
                  if(this.opponentBoard[boardI].cardEffect2=="Boost"){
                    this.opponentBoard[boardI+1].cardHealth += this.opponentBoard[boardI].cardEffectValue2
                    if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                    if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                    if(this.opponentBoard[boardI+1].cardEngineCondition=="Received Boost"){this.opponentBoard[boardI+1].cardEngineValue++}}
             else if(this.opponentBoard[boardI].cardEffect2=="Damage"){
                    if(this.opponentBoard[boardI+1].damageBondI){
                        this.opponentBoard[this.opponentBoard[this.opponentBoard[boardI+1]].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2
             } else if(this.opponentBoard[boardI+1].statusses[2].status=="Shield"){
                      this.opponentBoard[boardI+1].statusses[2]={}
                  } else {
                      if(boardI<8){if(this.opponentBoard[boardI+2].cardEffect!="Unkillable"){this.opponentBoard[boardI+1].cardHealth -= this.opponentBoard[boardI].cardEffectValue2}}
                      else{this.opponentBoard[boardI+1].cardHealth -= this.opponentBoard[boardI].cardEffectValue2}
                      if(this.opponentBoard[boardI+1].cardEngineCondition=="Damage Taken"){this.opponentBoard[boardI+1].cardEngineValue++}
                      if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                      if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                }}}}
       } else if(this.opponentBoard[boardI].cardEffectTarget2=="Adjacent"){
                if(boardI!=0){if(this.opponentBoard[boardI-1].cardName){
                    if(this.opponentBoard[boardI].cardEffect2=="Boost"){
                        this.opponentBoard[boardI-1].cardHealth += this.opponentBoard[boardI].cardEffectValue2
                        if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                        if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                        if(this.opponentBoard[boardI-1].cardEngineCondition=="Received Boost"){this.opponentBoard[boardI-1].cardEngineValue++
                        }}
                else if(this.opponentBoard[boardI].cardEffect2=="Damage"){
                        if(this.opponentBoard[boardI-1].damageBondI){
                            this.opponentBoard[this.opponentBoard[this.opponentBoard[boardI-1]].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2
                } else if(this.opponentBoard[boardI-1].statusses[2].status=="Shield"){
                        this.opponentBoard[boardI-1].statusses[2]={}
                    } else {
                        this.opponentBoard[boardI-1].cardHealth -= this.opponentBoard[boardI].cardEffectValue2
                        if(this.opponentBoard[boardI-1].cardEngineCondition=="Damage Taken"){this.opponentBoard[boardI-1].cardEngineValue++}
                        if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                        if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                }}}}
                if(boardI!=9){if(this.opponentBoard[boardI+1].cardName){
                    if(this.opponentBoard[boardI].cardEffect2=="Boost"){
                        this.opponentBoard[boardI+1].cardHealth += this.opponentBoard[boardI].cardEffectValue2
                        if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                        if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                        if(this.opponentBoard[boardI+1].cardEngineCondition=="Received Boost"){this.opponentBoard[boardI+1].cardEngineValue++
                        }}
                else if(this.opponentBoard[boardI].cardEffect2=="Damage"){
                        if(this.opponentBoard[boardI+1].damageBondI){
                            this.opponentBoard[this.opponentBoard[this.opponentBoard[boardI+1]].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2
                } else if(this.opponentBoard[boardI+1].statusses[2].status=="Shield"){
                        this.opponentBoard[boardI+1].statusses[2]={}
                    } else {
                        if(boardI<8){if(this.opponentBoard[boardI+2].cardEffect!="Unkillable"){this.opponentBoard[boardI+1].cardHealth -= this.opponentBoard[boardI].cardEffectValue2}}
                        else{this.opponentBoard[boardI+1].cardHealth -= this.opponentBoard[boardI].cardEffectValue2}
                        if(this.opponentBoard[boardI+1].cardEngineCondition=="Damage Taken"){this.opponentBoard[boardI+1].cardEngineValue++}
                        if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                        if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                }}}}
       } else if(this.opponentBoard[boardI].cardEffectTarget2=="Random"){
                  if(this.opponentBoard[boardI].cardTargetUnitType2=="Ally"){
                      if(this.filledOpponentBoardSpace.length>0){
                          let unitI = this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]
                          if(this.opponentBoard[boardI].cardEffect2=="Boost"){
                            this.opponentBoard[unitI].cardHealth += this.opponentBoard[boardI].cardEffectValue2
                            if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                            if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                            if(this.opponentBoard[unitI].cardEngineCondition=="Received Boost"){this.opponentBoard[unitI].cardEngineValue++}}
                     else if(this.opponentBoard[boardI].cardEffect2=="Damage"){
                            if(this.opponentBoard[unitI].damageBondI){
                              this.opponentBoard[this.opponentBoard[unitI].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2
                     } else if(this.opponentBoard[unitI].statusses[2].status=="Shield"){
                              this.opponentBoard[unitI].statusses[2]={}
                     } else {
                         if(unitI!=9){if(this.opponentBoard[unitI+1].cardEffect!="Unkillable"){this.opponentBoard[unitI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2}}
                         else{this.opponentBoard[unitI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2}
                         if(this.opponentBoard[unitI].cardEngineCondition=="Damage Taken"){this.opponentBoard[unitI].cardEngineValue++}
                         if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                         if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}
                        }}
           } else if(this.opponentBoard[boardI].cardTargetUnitType2=="Enemy"){
                      if(this.filledBoardSpace.length>0){
                          let unitI = this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]
                          if(this.opponentBoard[boardI].cardEffect2=="Boost"){
                            this.playerBoard[unitI].cardHealth += this.opponentBoard[boardI].cardEffectValue2
                            if(this.oppSpyI!=null) {this.opponentBoard[this.oppSpyI].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                            if(this.oppSpyI2!=null) {this.opponentBoard[this.oppSpyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                            if(this.playerBoard[unitI].cardEngineCondition=="Received Boost"){this.playerBoard[unitI].cardEngineValue++}}
                     else if(this.opponentBoard[boardI].cardEffect2=="Damage"){
                            if(this.playerBoard[unitI].damageBondI){
                              this.playerBoard[this.playerBoard[unitI].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2
                     } else if(this.playerBoard[unitI].statusses[2].status=="Shield"){
                              this.playerBoard[unitI].statusses[2]={}
                     } else {
                         if(unitI!=9){if(this.playerBoard[unitI+1].cardEffect!="Unkillable"){this.playerBoard[unitI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2}}
                         else{this.playerBoard[unitI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2}
                         if(this.playerBoard[unitI].cardEngineCondition=="Damage Taken"){this.playerBoard[unitI].cardEngineValue++}
                         if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                         if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}
                    }}
                        }
           } else if(this.opponentBoard[boardI].cardTargetUnitType2=="All"){
                    let side = Math.floor(Math.random() * 2)
                    if(side == 0){
                       if(this.filledOpponentBoardSpace.length>0){
                          let unitI = this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]
                          if(this.opponentBoard[boardI].cardEffect2=="Boost"){
                            this.opponentBoard[unitI].cardHealth += this.opponentBoard[boardI].cardEffectValue2
                            if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                            if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                            if(this.opponentBoard[unitI].cardEngineCondition=="Received Boost"){this.opponentBoard[unitI].cardEngineValue++}}
                     else if(this.opponentBoard[boardI].cardEffect2=="Damage"){
                            if(this.opponentBoard[unitI].damageBondI){
                              this.opponentBoard[this.opponentBoard[unitI].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2
                     } else if(this.opponentBoard[unitI].statusses[2].status=="Shield"){
                              this.opponentBoard[unitI].statusses[2]={}
                     } else {
                         if(unitI!=9){if(this.opponentBoard[unitI+1].cardEffect!="Unkillable"){this.opponentBoard[unitI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2}}
                         else{this.opponentBoard[unitI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2}
                         if(this.opponentBoard[unitI].cardEngineCondition=="Damage Taken"){this.opponentBoard[unitI].cardEngineValue++}
                         if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                         if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}
                        }}
             } else if(side == 1){
                      if(this.filledBoardSpace.length>0){
                          let unitI = this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]
                          if(this.opponentBoard[boardI].cardEffect2=="Boost"){
                            this.playerBoard[unitI].cardHealth += this.opponentBoard[boardI].cardEffectValue2
                            if(this.oppSpyI!=null) {this.opponentBoard[this.oppSpyI].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                            if(this.oppSpyI2!=null) {this.opponentBoard[this.oppSpyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                            if(this.playerBoard[unitI].cardEngineCondition=="Received Boost"){this.playerBoard[unitI].cardEngineValue++}}
                     else if(this.opponentBoard[boardI].cardEffect2=="Damage"){
                            if(this.playerBoard[unitI].damageBondI){
                              this.playerBoard[this.playerBoard[unitI].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2
                     } else if(this.playerBoard[unitI].statusses[2].status=="Shield"){
                              this.playerBoard[unitI].statusses[2]={}
                     } else {
                         if(unitI!=9){if(this.playerBoard[unitI+1].cardEffect!="Unkillable"){this.playerBoard[unitI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2}}
                         else{this.playerBoard[unitI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2}
                         if(this.playerBoard[unitI].cardEngineCondition=="Damage Taken"){this.playerBoard[unitI].cardEngineValue++}
                         if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                         if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}
                    }}
                }
             }
           }
       } else if(this.opponentBoard[boardI].cardEffectTarget2=="All Allies"){
           for(let i = 0; i < this.filledOpponentBoardSpace.length; i++){
               if(this.opponentBoard[boardI].cardEffect2=="Boost"){
                    this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth += this.opponentBoard[boardI].cardEffectValue2
                    if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                    if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                    if(this.opponentBoard[this.filledOpponentBoardSpace[i]].cardEngineCondition=="Received Boost"){this.opponentBoard[this.filledOpponentBoardSpace[i]].cardEngineValue++}}
             else if(this.opponentBoard[boardI].cardEffect2=="Damage"){
                    if(this.opponentBoard[this.filledOpponentBoardSpace[i]].damageBondI){
                        this.opponentBoard[this.opponentBoard[this.opponentBoard[this.filledOpponentBoardSpace[i]]].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2
             } else if(this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[2].status=="Shield"){
                      this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[2]={}
                  } else {
                      if(this.filledOpponentBoardSpace[i]!=9){if(this.opponentBoard[this.filledOpponentBoardSpace[i]+1].cardEffect!="Unkillable"){this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth -= this.opponentBoard[boardI].cardEffectValue2}}
                      else{this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth -= this.opponentBoard[boardI].cardEffectValue2}
                      if(this.opponentBoard[this.filledOpponentBoardSpace[i]].cardEngineCondition=="Damage Taken"){this.opponentBoard[this.filledOpponentBoardSpace[i]].cardEngineValue++}
                      if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                      if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}}
           }
       } else if(this.opponentBoard[boardI].cardEffectTarget2=="All Enemies"){
           for(let i = 0; i < this.filledBoardSpace.length; i++){
               if(this.opponentBoard[boardI].cardEffect2=="Boost"){
                    this.playerBoard[this.filledBoardSpace[i]].cardHealth += this.opponentBoard[boardI].cardEffectValue2
                    if(this.oppSpyI!=null) {this.opponentBoard[this.oppSpyI].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                    if(this.oppSpyI2!=null) {this.opponentBoard[this.oppSpyI2].cardHealth += this.opponentBoard[boardI].cardEffectValue2}
                    if(this.playerBoard[this.filledBoardSpace[i]].cardEngineCondition=="Received Boost"){this.playerBoard[this.filledBoardSpace[i]].cardEngineValue++}}
             else if(this.opponentBoard[boardI].cardEffect2=="Damage"){
                    if(this.playerBoard[this.filledBoardSpace[i]].damageBondI){
                        this.playerBoard[this.playerBoard[this.playerBoard[this.filledBoardSpace[i]]].damageBondI].cardHealth -= this.opponentBoard[boardI].cardEffectValue2
             } else if(this.playerBoard[this.filledBoardSpace[i]].statusses[2].status=="Shield"){
                      this.playerBoard[this.filledBoardSpace[i]].statusses[2]={}
                  } else {
                      if(this.filledBoardSpace[i]!=9){if(this.playerBoard[this.filledBoardSpace[i]+1].cardEffect!="Unkillable"){this.playerBoard[this.filledBoardSpace[i]].cardHealth -= this.opponentBoard[boardI].cardEffectValue2}}
                      else{this.playerBoard[this.filledBoardSpace[i]].cardHealth -= this.opponentBoard[boardI].cardEffectValue2}
                      if(this.playerBoard[this.filledBoardSpace[i]].cardEngineCondition=="Damage Taken"){this.playerBoard[this.filledBoardSpace[i]].cardEngineValue++}
                      if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                      if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}
                    }}
           }
          }}
          if(this.opponentBoard[boardI].cardEffect=="Status" && this.opponentBoard[boardI].cardEffectTarget!="Manual"){
              let duration = 0
              if(this.opponentBoard[boardI].cardStatusDuration){duration = this.opponentBoard[boardI].cardStatusDuration}
              if(this.opponentBoard[boardI].cardEffectTarget=="Self"){
                if(this.opponentBoard[boardI].cardStatus=="Bleeding"){
                    if(this.opponentBoard[boardI].statusses[0].duration && this.opponentBoard[boardI].statusses[0].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration + this.opponentBoard[boardI].statusses[0].duration}   
                    this.opponentBoard[boardI].statusses[0] = {status: this.opponentBoard[boardI].cardStatus, duration}
         } else if(this.opponentBoard[boardI].cardStatus=="Vitality"){
                    if(this.opponentBoard[boardI].statusses[1].duration && this.opponentBoard[boardI].statusses[1].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration + this.opponentBoard[boardI].statusses[1].duration}   
                    this.opponentBoard[boardI].statusses[1] = {status: this.opponentBoard[boardI].cardStatus, duration}
         } else if(this.opponentBoard[boardI].cardStatus=="Shield"){this.opponentBoard[boardI].statusses[2] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
           else if(this.opponentBoard[boardI].cardStatus=="Freeze"){this.opponentBoard[boardI].statusses[3] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
       } else if(this.opponentBoard[boardI].cardEffectTarget=="Left"){
                if(boardI!=0){if(this.opponentBoard[boardI-1].cardName){
                  if(this.opponentBoard[boardI].cardStatus=="Bleeding"){
                    if(this.opponentBoard[boardI-1].statusses[0].duration && this.opponentBoard[boardI-1].statusses[0].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration + this.opponentBoard[boardI-1].statusses[0].duration}   
                    this.opponentBoard[boardI-1].statusses[0] = {status: this.opponentBoard[boardI].cardStatus, duration}
           } else if(this.opponentBoard[boardI].cardStatus=="Vitality"){
                    if(this.opponentBoard[boardI-1].statusses[1].duration && this.opponentBoard[boardI-1].statusses[1].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration + this.opponentBoard[boardI-1].statusses[1].duration}   
                    this.opponentBoard[boardI-1].statusses[1] = {status: this.opponentBoard[boardI].cardStatus, duration}
           } else if(this.opponentBoard[boardI].cardStatus=="Shield"){this.opponentBoard[boardI-1].statusses[2] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
             else if(this.opponentBoard[boardI].cardStatus=="Freeze"){this.opponentBoard[boardI-1].statusses[3] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
                }}
       } else if(this.opponentBoard[boardI].cardEffectTarget=="Right"){
                  if(boardI!=9){if(this.opponentBoard[boardI+1].cardName){
                    if(this.opponentBoard[boardI].cardStatus=="Bleeding"){
                    if(this.opponentBoard[boardI+1].statusses[0].duration && this.opponentBoard[boardI+1].statusses[0].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration + this.opponentBoard[boardI+1].statusses[0].duration}   
                    this.opponentBoard[boardI+1].statusses[0] = {status: this.opponentBoard[boardI].cardStatus, duration}
             } else if(this.opponentBoard[boardI].cardStatus=="Vitality"){
                    if(this.opponentBoard[boardI+1].statusses[1].duration && this.opponentBoard[boardI+1].statusses[1].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration + this.opponentBoard[boardI+1].statusses[1].duration}   
                    this.opponentBoard[boardI+1].statusses[1] = {status: this.opponentBoard[boardI].cardStatus, duration}
             } else if(this.opponentBoard[boardI].cardStatus=="Shield"){this.opponentBoard[boardI + 1].statusses[2] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
               else if(this.opponentBoard[boardI].cardStatus=="Freeze"){this.opponentBoard[boardI + 1].statusses[3] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
                }}
       } else if(this.opponentBoard[boardI].cardEffectTarget=="Adjacent"){
                if(boardI!=0){if(this.opponentBoard[boardI-1].cardName){
                    if(this.opponentBoard[boardI].cardStatus=="Bleeding"){
                        if(this.opponentBoard[boardI-1].statusses[0].duration && this.opponentBoard[boardI-1].statusses[0].duration>0){
                            duration = this.opponentBoard[boardI].cardStatusDuration + this.opponentBoard[boardI-1].statusses[0].duration}   
                        this.opponentBoard[boardI-1].statusses[0] = {status: this.opponentBoard[boardI].cardStatus, duration}
                } else if(this.opponentBoard[boardI].cardStatus=="Vitality"){
                        if(this.opponentBoard[boardI-1].statusses[1].duration && this.opponentBoard[boardI-1].statusses[1].duration>0){
                            duration = this.opponentBoard[boardI].cardStatusDuration + this.opponentBoard[boardI-1].statusses[1].duration}   
                        this.opponentBoard[boardI-1].statusses[1] = {status: this.opponentBoard[boardI].cardStatus, duration}
                } else if(this.opponentBoard[boardI].cardStatus=="Shield"){this.opponentBoard[boardI - 1].statusses[2] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
                else if(this.opponentBoard[boardI].cardStatus=="Freeze"){this.opponentBoard[boardI - 1].statusses[3] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
                }}
                if(boardI!=0){if(this.opponentBoard[boardI+1].cardName){
                    if(this.opponentBoard[boardI].cardStatus=="Bleeding"){
                        if(this.opponentBoard[boardI+1].statusses[0].duration && this.opponentBoard[boardI+1].statusses[0].duration>0){
                            duration = this.opponentBoard[boardI].cardStatusDuration + this.opponentBoard[boardI+1].statusses[0].duration}   
                        this.opponentBoard[boardI+1].statusses[0] = {status: this.opponentBoard[boardI].cardStatus, duration}
                } else if(this.opponentBoard[boardI].cardStatus=="Vitality"){
                        if(this.opponentBoard[boardI+1].statusses[1].duration && this.opponentBoard[boardI+1].statusses[1].duration>0){
                            duration = this.opponentBoard[boardI].cardStatusDuration + this.opponentBoard[boardI+1].statusses[1].duration}   
                        this.opponentBoard[boardI+1].statusses[1] = {status: this.opponentBoard[boardI].cardStatus, duration}
                } else if(this.opponentBoard[boardI].cardStatus=="Shield"){this.opponentBoard[boardI + 1].statusses[2] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
                else if(this.opponentBoard[boardI].cardStatus=="Freeze"){this.opponentBoard[boardI + 1].statusses[3] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
                }}
       } else if(this.opponentBoard[boardI].cardEffectTarget=="Random"){
                  if(this.opponentBoard[boardI].cardTargetUnitType=="Ally"){
                      if(this.filledOpponentBoardSpace.length>0){
                          let unit = this.opponentBoard[this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]]
                          if(this.opponentBoard[boardI].cardStatus=="Bleeding"){
                    if(unit.statusses[0].duration && unit.statusses[0].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration + unit.statusses[0].duration}   
                    unit.statusses[0] = {status: this.opponentBoard[boardI].cardStatus, duration}
                   } else if(this.opponentBoard[boardI].cardStatus=="Vitality"){
                    if(unit.statusses[1].duration && unit.statusses[1].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration + unit.statusses[1].duration}   
                    unit.statusses[1] = {status: this.opponentBoard[boardI].cardStatus, duration}
                   } else if(this.opponentBoard[boardI].cardStatus=="Shield"){unit.statusses[2] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
                     else if(this.opponentBoard[boardI].cardStatus=="Freeze"){unit.statusses[3] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
                        }
           } else if(this.opponentBoard[boardI].cardTargetUnitType=="Enemy") {
                      if(this.filledBoardSpace.length>0){
                          let unit = this.playerBoard[this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]]
                          if(this.opponentBoard[boardI].cardStatus=="Bleeding"){
                    if(unit.statusses[0].duration && unit.statusses[0].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration + unit.statusses[0].duration}   
                    unit.statusses[0] = {status: this.opponentBoard[boardI].cardStatus, duration}
                   } else if(this.opponentBoard[boardI].cardStatus=="Vitality"){
                    if(unit.statusses[1].duration && unit.statusses[1].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration + unit.statusses[1].duration}   
                    unit.statusses[1] = {status: this.opponentBoard[boardI].cardStatus, duration}
                   } else if(this.opponentBoard[boardI].cardStatus=="Shield"){unit.statusses[2] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
                     else if(this.opponentBoard[boardI].cardStatus=="Freeze"){unit.statusses[3] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
                        }
           } else if(this.opponentBoard[boardI].cardTargetUnitType=="All"){
                    let side = Math.floor(Math.random() * 2)
                    let unit
                    if(side == 0){
                          unit = this.opponentBoard[this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]]
             } else if(side == 1){
                          unit = this.playerBoard[this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]]
             }      if(this.opponentBoard[boardI].cardStatus=="Bleeding"){
                    if(unit.statusses[0].duration && unit.statusses[0].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration + unit.statusses[0].duration}   
                    unit.statusses[0] = {status: this.opponentBoard[boardI].cardStatus, duration}
             } else if(this.opponentBoard[boardI].cardStatus=="Vitality"){
                    if(unit.statusses[1].duration && unit.statusses[1].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration + unit.statusses[1].duration}   
                    unit.statusses[1] = {status: this.opponentBoard[boardI].cardStatus, duration}
             } else if(this.opponentBoard[boardI].cardStatus=="Shield"){unit.statusses[2] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
               else if(this.opponentBoard[boardI].cardStatus=="Freeze"){unit.statusses[3] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
           }
       } else if(this.opponentBoard[boardI].cardEffectTarget=="All Allies"){
           for(let i = 0; i < this.filledOpponentBoardSpace.length; i++){
                 if(this.opponentBoard[boardI].cardStatus=="Bleeding"){
                    if(this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0].duration && this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration + this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0].duration}   
                    this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0] = {status: this.opponentBoard[boardI].cardStatus, duration}
          } else if(this.opponentBoard[boardI].cardStatus=="Vitality"){
                    if(this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1].duration && this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration + this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1].duration}   
                    this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1] = {status: this.opponentBoard[boardI].cardStatus, duration}
          } else if(this.opponentBoard[boardI].cardStatus=="Shield"){this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[2] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
            else if(this.opponentBoard[boardI].cardStatus=="Freeze"){this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[3] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
            if(this.opponentBoard[boardI].cardStatusDuration){duration = this.opponentBoard[boardI].cardStatusDuration}
           }
       } else if(this.opponentBoard[boardI].cardEffectTarget=="All Enemies"){
           for(let i = 0; i < this.filledBoardSpace.length; i++){
                if(this.opponentBoard[boardI].cardStatus=="Bleeding"){
                    if(this.playerBoard[this.filledBoardSpace[i]].statusses[0].duration && this.playerBoard[this.filledBoardSpace[i]].statusses[0].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration + this.playerBoard[this.filledBoardSpace[i]].statusses[0].duration}   
                    this.playerBoard[this.filledBoardSpace[i]].statusses[0] = {status: this.opponentBoard[boardI].cardStatus, duration}
         } else if(this.opponentBoard[boardI].cardStatus=="Vitality"){
                    if(this.playerBoard[this.filledBoardSpace[i]].statusses[1].duration && this.playerBoard[this.filledBoardSpace[i]].statusses[1].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration + this.playerBoard[this.filledBoardSpace[i]].statusses[1].duration}   
                    this.playerBoard[this.filledBoardSpace[i]].statusses[1] = {status: this.opponentBoard[boardI].cardStatus, duration}
         } else if(this.opponentBoard[boardI].cardStatus=="Shield"){this.playerBoard[this.filledBoardSpace[i]].statusses[2] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
           else if(this.opponentBoard[boardI].cardStatus=="Freeze"){this.playerBoard[this.filledBoardSpace[i]].statusses[3] = {status: this.opponentBoard[boardI].cardStatus, duration: 999}}
           if(this.opponentBoard[boardI].cardStatusDuration){duration = this.opponentBoard[boardI].cardStatusDuration}
           }
          }}
          if(this.opponentBoard[boardI].cardEffect2=="Status" && this.opponentBoard[boardI].cardEffectTarget2!="Manual"){
              let duration = 0
              if(this.opponentBoard[boardI].cardStatusDuration2){duration = this.opponentBoard[boardI].cardStatusDuration2}
              if(this.opponentBoard[boardI].cardEffectTarget2=="Self"){
                if(this.opponentBoard[boardI].cardStatus2=="Bleeding"){
                    if(this.opponentBoard[boardI].statusses[0].duration && this.opponentBoard[boardI].statusses[0].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration2 + this.opponentBoard[boardI].statusses[0].duration}   
                    this.opponentBoard[boardI].statusses[0] = {status: this.opponentBoard[boardI].cardStatus2, duration}
         } else if(this.opponentBoard[boardI].cardStatus2=="Vitality"){
                    if(this.opponentBoard[boardI].statusses[1].duration && this.opponentBoard[boardI].statusses[1].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration2 + this.opponentBoard[boardI].statusses[1].duration}   
                    this.opponentBoard[boardI].statusses[1] = {status: this.opponentBoard[boardI].cardStatus2, duration}
         } else if(this.opponentBoard[boardI].cardStatus2=="Shield"){this.opponentBoard[boardI].statusses[2] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
           else if(this.opponentBoard[boardI].cardStatus2=="Freeze"){this.opponentBoard[boardI].statusses[3] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
       } else if(this.opponentBoard[boardI].cardEffectTarget2=="Left"){
                if(boardI!=0){if(this.opponentBoard[boardI-1].cardName){
                    if(this.opponentBoard[boardI].cardStatus2=="Bleeding"){
                        if(this.opponentBoard[boardI-1].statusses[0].duration && this.opponentBoard[boardI-1].statusses[0].duration>0){
                            duration = this.opponentBoard[boardI].cardStatusDuration2 + this.opponentBoard[boardI-1].statusses[0].duration}   
                        this.opponentBoard[boardI-1].statusses[0] = {status: this.opponentBoard[boardI].cardStatus2, duration}
            } else if(this.opponentBoard[boardI].cardStatus2=="Vitality"){
                        if(this.opponentBoard[boardI-1].statusses[1].duration && this.opponentBoard[boardI-1].statusses[1].duration>0){
                            duration = this.opponentBoard[boardI].cardStatusDuration2 + this.opponentBoard[boardI-1].statusses[1].duration}   
                        this.opponentBoard[boardI-1].statusses[1] = {status: this.opponentBoard[boardI].cardStatus2, duration}
            } else if(this.opponentBoard[boardI].cardStatus2=="Shield"){this.opponentBoard[boardI-1].statusses[2] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
                else if(this.opponentBoard[boardI].cardStatus2=="Freeze"){this.opponentBoard[boardI-1].statusses[3] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
                }}
       } else if(this.opponentBoard[boardI].cardEffectTarget2=="Right"){
                  if(boardI!=9){if(this.opponentBoard[boardI+1].cardName){
                        if(this.opponentBoard[boardI].cardStatus2=="Bleeding"){
                        if(this.opponentBoard[boardI+1].statusses[0].duration && this.opponentBoard[boardI+1].statusses[0].duration>0){
                            duration = this.opponentBoard[boardI].cardStatusDuration2 + this.opponentBoard[boardI+1].statusses[0].duration}   
                        this.opponentBoard[boardI+1].statusses[0] = {status: this.opponentBoard[boardI].cardStatus2, duration}
                } else if(this.opponentBoard[boardI].cardStatus2=="Vitality"){
                        if(this.opponentBoard[boardI+1].statusses[1].duration && this.opponentBoard[boardI+1].statusses[1].duration>0){
                            duration = this.opponentBoard[boardI].cardStatusDuration2 + this.opponentBoard[boardI+1].statusses[1].duration}   
                        this.opponentBoard[boardI+1].statusses[1] = {status: this.opponentBoard[boardI].cardStatus2, duration}
                } else if(this.opponentBoard[boardI].cardStatus2=="Shield"){this.opponentBoard[boardI + 1].statusses[2] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
                else if(this.opponentBoard[boardI].cardStatus2=="Freeze"){this.opponentBoard[boardI + 1].statusses[3] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
                }}
       } else if(this.opponentBoard[boardI].cardEffectTarget2=="Adjacent"){
                if(boardI!=0){if(this.opponentBoard[boardI-1].cardName){
                    if(this.opponentBoard[boardI].cardStatus2=="Bleeding"){
                        if(this.opponentBoard[boardI-1].statusses[0].duration && this.opponentBoard[boardI-1].statusses[0].duration>0){
                            duration = this.opponentBoard[boardI].cardStatusDuration2 + this.opponentBoard[boardI-1].statusses[0].duration}   
                        this.opponentBoard[boardI-1].statusses[0] = {status: this.opponentBoard[boardI].cardStatus2, duration}
                } else if(this.opponentBoard[boardI].cardStatus2=="Vitality"){
                        if(this.opponentBoard[boardI-1].statusses[1].duration && this.opponentBoard[boardI-1].statusses[1].duration>0){
                            duration = this.opponentBoard[boardI].cardStatusDuration2 + this.opponentBoard[boardI-1].statusses[1].duration}   
                        this.opponentBoard[boardI-1].statusses[1] = {status: this.opponentBoard[boardI].cardStatus2, duration}
                } else if(this.opponentBoard[boardI].cardStatus2=="Shield"){this.opponentBoard[boardI - 1].statusses[2] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
                else if(this.opponentBoard[boardI].cardStatus2=="Freeze"){this.opponentBoard[boardI - 1].statusses[3] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
                }}
                if(boardI!=9){if(this.opponentBoard[boardI+1].cardName){
                    if(this.opponentBoard[boardI].cardStatus2=="Bleeding"){
                        if(this.opponentBoard[boardI+1].statusses[0].duration && this.opponentBoard[boardI+1].statusses[0].duration>0){
                            duration = this.opponentBoard[boardI].cardStatusDuration2 + this.opponentBoard[boardI+1].statusses[0].duration}   
                        this.opponentBoard[boardI+1].statusses[0] = {status: this.opponentBoard[boardI].cardStatus2, duration}
                } else if(this.opponentBoard[boardI].cardStatus2=="Vitality"){
                        if(this.opponentBoard[boardI+1].statusses[1].duration && this.opponentBoard[boardI+1].statusses[1].duration>0){
                            duration = this.opponentBoard[boardI].cardStatusDuration2 + this.opponentBoard[boardI+1].statusses[1].duration}   
                        this.opponentBoard[boardI+1].statusses[1] = {status: this.opponentBoard[boardI].cardStatus2, duration}
                } else if(this.opponentBoard[boardI].cardStatus2=="Shield"){this.opponentBoard[boardI + 1].statusses[2] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
                else if(this.opponentBoard[boardI].cardStatus2=="Freeze"){this.opponentBoard[boardI + 1].statusses[3] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
                }}
       } else if(this.opponentBoard[boardI].cardEffectTarget2=="Random"){
                  if(this.opponentBoard[boardI].cardTargetUnitType2=="Ally"){
                      if(this.filledOpponentBoardSpace.length>0){
                          let unit = this.opponentBoard[this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]]
                          if(this.opponentBoard[boardI].cardStatus2=="Bleeding"){
                    if(unit.statusses[0].duration && unit.statusses[0].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration2 + unit.statusses[0].duration}   
                    unit.statusses[0] = {status: this.opponentBoard[boardI].cardStatus2, duration}
                   } else if(this.opponentBoard[boardI].cardStatus2=="Vitality"){
                    if(unit.statusses[1].duration && unit.statusses[1].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration2 + unit.statusses[1].duration}   
                    unit.statusses[1] = {status: this.opponentBoard[boardI].cardStatus2, duration}
                   } else if(this.opponentBoard[boardI].cardStatus2=="Shield"){unit.statusses[2] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
                     else if(this.opponentBoard[boardI].cardStatus2=="Freeze"){unit.statusses[3] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
                        }
           } else if(this.opponentBoard[boardI].cardTargetUnitType2=="Enemy") {
                      if(this.filledBoardSpace.length>0){
                          let unit = this.playerBoard[this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]]
                          if(this.opponentBoard[boardI].cardStatus2=="Bleeding"){
                    if(unit.statusses[0].duration && unit.statusses[0].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration2 + unit.statusses[0].duration}   
                    unit.statusses[0] = {status: this.opponentBoard[boardI].cardStatus2, duration}
                   } else if(this.opponentBoard[boardI].cardStatus2=="Vitality"){
                    if(unit.statusses[1].duration && unit.statusses[1].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration2 + unit.statusses[1].duration}   
                    unit.statusses[1] = {status: this.opponentBoard[boardI].cardStatus2, duration}
                   } else if(this.opponentBoard[boardI].cardStatus2=="Shield"){unit.statusses[2] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
                     else if(this.opponentBoard[boardI].cardStatus2=="Freeze"){unit.statusses[3] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
                        }
           } else if(this.opponentBoard[boardI].cardTargetUnitType2=="All"){
                    let side = Math.floor(Math.random() * 2)
                    let unit
                    if(side == 0){
                          unit = this.opponentBoard[this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]]
             } else if(side == 1){
                          unit = this.playerBoard[this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]]
             }      if(this.opponentBoard[boardI].cardStatus2=="Bleeding"){
                    if(unit.statusses[0].duration && unit.statusses[0].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration2 + unit.statusses[0].duration}   
                    unit.statusses[0] = {status: this.opponentBoard[boardI].cardStatus2, duration}
             } else if(this.opponentBoard[boardI].cardStatus2=="Vitality"){
                    if(unit.statusses[1].duration && unit.statusses[1].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration2 + unit.statusses[1].duration}   
                    unit.statusses[1] = {status: this.opponentBoard[boardI].cardStatus2, duration}
             } else if(this.opponentBoard[boardI].cardStatus2=="Shield"){unit.statusses[2] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
               else if(this.opponentBoard[boardI].cardStatus2=="Freeze"){unit.statusses[3] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
           }
       } else if(this.opponentBoard[boardI].cardEffectTarget2=="All Allies"){
           for(let i = 0; i < this.filledOpponentBoardSpace.length; i++){
                 if(this.opponentBoard[boardI].cardStatus2=="Bleeding"){
                    if(this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0].duration && this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration2 + this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0].duration}   
                    this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0] = {status: this.opponentBoard[boardI].cardStatus2, duration}
          } else if(this.opponentBoard[boardI].cardStatus2=="Vitality"){
                    if(this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1].duration && this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration2 + this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1].duration}   
                    this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1] = {status: this.opponentBoard[boardI].cardStatus2, duration}
          } else if(this.opponentBoard[boardI].cardStatus2=="Shield"){this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[2] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
            else if(this.opponentBoard[boardI].cardStatus2=="Freeze"){this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[3] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
            if(this.opponentBoard[boardI].cardStatusDuration2){duration = this.opponentBoard[boardI].cardStatusDuration2}
           }
       } else if(this.opponentBoard[boardI].cardEffectTarget2=="All Enemies"){
           for(let i = 0; i < this.filledBoardSpace.length; i++){
                if(this.opponentBoard[boardI].cardStatus2=="Bleeding"){
                    if(this.playerBoard[this.filledBoardSpace[i]].statusses[0].duration && this.playerBoard[this.filledBoardSpace[i]].statusses[0].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration2 + this.playerBoard[this.filledBoardSpace[i]].statusses[0].duration}   
                    this.playerBoard[this.filledBoardSpace[i]].statusses[0] = {status: this.opponentBoard[boardI].cardStatus2, duration}
         } else if(this.opponentBoard[boardI].cardStatus2=="Vitality"){
                    if(this.playerBoard[this.filledBoardSpace[i]].statusses[1].duration && this.playerBoard[this.filledBoardSpace[i]].statusses[1].duration>0){
                        duration = this.opponentBoard[boardI].cardStatusDuration2 + this.playerBoard[this.filledBoardSpace[i]].statusses[1].duration}   
                    this.playerBoard[this.filledBoardSpace[i]].statusses[1] = {status: this.opponentBoard[boardI].cardStatus2, duration}
         } else if(this.opponentBoard[boardI].cardStatus2=="Shield"){this.playerBoard[this.filledBoardSpace[i]].statusses[2] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
           else if(this.opponentBoard[boardI].cardStatus2=="Freeze"){this.playerBoard[this.filledBoardSpace[i]].statusses[3] = {status: this.opponentBoard[boardI].cardStatus2, duration: 999}}
           if(this.opponentBoard[boardI].cardStatusDuration2){duration = this.opponentBoard[boardI].cardStatusDuration2}
           }
          }}
          if(this.opponentBoard[boardI].cardEffect=="Reveal" && this.playerHand.length>0){
              if(this.opponentBoard[boardI].cardEffectTarget=="Random"){
                  let hiddenCardIndex = []
                  let playerHandCardsI = []
                  for(let o = 0; o < 10; o++){
                      if(this.playerHand[o].cardName){playerHandCardsI.push(o)}
                  }
                  for(let i = 0; i < playerHandCardsI.length; i++){
                      if(this.playerHand[playerHandCardsI[i]].cardName){
                          if(this.playerHand[playerHandCardsI[i]].revealed==false){
                              hiddenCardIndex.push(playerHandCardsI[i])
                          }
                      }
                  }
                for(let i = 0; i < this.opponentBoard[boardI].cardEffectValue; i++){
                    if(hiddenCardIndex.length>0){
                        let revealCardI = hiddenCardIndex[Math.floor(Math.random() * hiddenCardIndex.length)]
                        this.playerHand[revealCardI].revealed=true
                        hiddenCardIndex.splice(hiddenCardIndex.indexOf(revealCardI), 1)
                    }
              } hiddenCardIndex=[]}
          }
          if(this.opponentBoard[boardI].cardEffect=="Engine" || this.opponentBoard[boardI].cardEffect2=="Engine"){
              if(this.opponentBoard[boardI].cardEngineCondition=="Allied Unit Damaged" && this.oppChiefI){this.oppChiefI2=boardI}
              else if(this.opponentBoard[boardI].cardEngineCondition=="Allied Unit Damaged"){this.oppChiefI=boardI}
              if(this.opponentBoard[boardI].cardEngineCondition=="Enemy Boosted" && this.oppSpyI){this.oppSpyI2=boardI}
              else if(this.opponentBoard[boardI].cardEngineCondition=="Enemy Boosted"){this.oppSpyI=boardI}4
              this.opponentEngines.push([this.opponentBoard[boardI], boardI])
          }
          if(this.opponentBoard[boardI].cardEffect=="Grave Consume" && this.opponentGraveyard.length>0){
              this.consumedUnitType=this.opponentBoard[boardI].consumeType
              let consumableUnits = []
              let highestHP = 0
              for (let i = 0; i < this.opponentGraveyard.length; i++){
                  if(this.opponentGraveyard[i].cardRarity==this.consumedUnitType){consumableUnits.push([this.opponentGraveyard[i], i])}
              }
              if(consumableUnits.length>0){
                  let consumedI
                  for(let i = 0; i < consumableUnits.length; i++){
                      if(consumableUnits[i][0].cardBaseHealth > highestHP){
                          highestHP = consumableUnits[i][0].cardBaseHealth
                          consumedI = i
                      }
                  }
                  this.opponentBoard[boardI].cardHealth += highestHP
                  this.opponentGraveyard.splice([consumableUnits[consumedI][1]], 1)
              }
          }
          if(this.opponentBoard[boardI].cardEffect=="Copy Grave Unit" && this.opponentGraveyard.length>0){
              let goldCards = []
              let silverCards = []
              for(let i = 0; i < this.opponentGraveyard.length; i++){
                  if(this.opponentGraveyard[i].cardRarity=="Gold"){goldCards.push(this.opponentGraveyard[i])
           } else if(this.opponentGraveyard[i].cardRarity=="Silver"){silverCards.push(this.opponentGraveyard[i])} 
              }
              let copiedCard = null
              if(goldCards.length>0){
                copiedCard = goldCards[Math.floor(Math.random() * goldCards.length)]
            } else if(silverCards.length>0){
                copiedCard = silverCards[Math.floor(Math.random() * silverCards.length)]
            } else {
                copiedCard = this.opponentGraveyard[Math.floor(Math.random() * this.opponentGraveyard.length)]
            }
              if(copiedCard!=null){
                  if(copiedCard.cardEffect=="Engine"){
                    if(copiedCard.cardEngineCondition=="Allied Unit Damaged" && this.oppChiefI!=null){this.oppChiefI2=boardI}
               else if(copiedCard.cardEngineCondition=="Allied Unit Damaged"){this.oppChiefI=boardI}
                    if(copiedCard.cardEngineCondition=="Enemy Boosted" && this.oppSpyI!=null){this.oppSpyI2=boardI}
               else if(copiedCard.cardEngineCondition=="Enemy Boosted"){this.oppSpyI=boardI}
                        this.opponentEngines.push([copiedCard, boardI])
                    }
              this.opponentBoard[boardI] = copiedCard
              this.opponentBoard[boardI].cardAmount++
              this.opponentBoard[boardI].cardHealth = copiedCard.cardBaseHealth
              }
          }
          if(this.opponentBoard[boardI].cardEffect=="Play Card"){
            setTimeout(() => {   
              if(this.opponentBoard[boardI].playedCard=="Enemy Top Deck"){
                  this.chosenEnemyPlayableCard=null
                  this.chosenEnemyPlayableCard = this.playerDeck.shift()
                  this.playEnemyCard()
       } else if(this.opponentBoard[boardI].playedCard=="Any Card From Own Deck"){
                  if(this.opponentDeck.length){
                    let deckI = []
                    for(let i = 0; i < this.opponentDeck.length; i++){if(this.opponentDeck[i].cardName!=undefined){deckI.push(i)}}
                    console.log(`opponentDeck: ${this.opponentDeck}, deckI: ${deckI}`)
                    let index = this.chooseEnemyCard(this.opponentDeck, deckI)
                    this.chosenEnemyPlayableCard = this.opponentDeck[index]
                    console.log(`thechosencard: ${this.chosenEnemyPlayableCard}`)
                    this.playEnemyCard()
                    this.opponentDeck.splice(index, 1)
                  }  
       } else if(this.opponentBoard[boardI].playedCard=="Revealed Card In Opponent Hand"){
                  let revealedCards = []
                  for(let i = 0; i < this.playerHand.length; i++){
                      if(this.playerHand[i].revealed){revealedCards.push(this.playerHand[i])}
                  }
                  if(revealedCards.length){
                    let revealedI = [];
                    for(let i = 0; i < revealedCards.length; i++){if(revealedCards[i].cardName!=undefined){revealedI.push(i)}}
                    this.chosenEnemyPlayableCard = revealedCards[this.chooseEnemyCard(revealedCards, revealedI)];
                    this.playEnemyCard()
                  }  
       }}, 500)
          }
          if(this.opponentBoard[boardI].cardEffect=="Set Health"){
              if(this.opponentBoard[boardI].cardEffectTarget=="All Units"){
                  for(let i = 0; i < this.filledOpponentBoardSpace.length; i++){
                      if(this.filledOpponentBoardSpace[i] != boardI){this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth = this.opponentBoard[boardI].cardEffectValue}
                  }
                  for(let o = 0; o < this.filledBoardSpace.length; o++){
                      this.playerBoard[this.filledBoardSpace[o]].cardHealth = this.opponentBoard[boardI].cardEffectValue
                  }
              }
          }
          if(this.opponentBoard[boardI].cardEffectTarget=="Manual"){
              let pass = true
              if(this.opponentBoard[boardI].cardTargetUnitType=="Ally" && this.filledOpponentBoardSpace.length<2){
                  pass = false
              }
              if(this.opponentBoard[boardI].cardTargetUnitType=="Enemy" && this.filledBoardSpace.length==0){
                  pass = false
              }
              if(pass){this.processEnemyDeploy()}

              this.chosenEnemyCardHealth = null
              this.chosenEnemyCardEffect = ""
              this.chosenEnemyCardTarget = ""
              this.chosenEnemyCardTargetType = ""
              this.chosenEnemyCardEffectValue = null
              this.chosenEnemyCardStatus = ""
              this.chosenEnemyCardStatusDuration = null
              this.chosenEnemyCardEngineEffect = ""
              this.chosenEnemyCardTarget = ""
            
          }
          if(this.opponentBoard[boardI].cardEffect=="Removal"){
              let pass = false
              for(let i = 0; i < this.filledBoardSpace.length; i++){
                  if(this.chosenEnemyCardRemovalCondition=="Above Value"){if(this.playerBoard[this.filledBoardSpace[i]].cardHealth>this.chosenEnemyCardRemovalConditionValue){pass=true}}
                  if(this.chosenEnemyCardRemovalCondition=="Bleeding Enemy Health"){if(this.playerBoard[this.filledBoardSpace[i]].statusses[0].duration){pass=true}}
              }
              if(pass){this.processEnemyDeploy()}
              else {
                  this.chosenEnemyCardHealth = null
                  this.chosenEnemyCardEffect = ""
                  this.chosenEnemyCardTarget = ""
                  this.chosenEnemyCardTargetType = ""
                  this.chosenEnemyCardEffectValue = null
                  this.chosenEnemyCardStatus = ""
                  this.chosenEnemyCardStatusDuration = null
                  this.chosenEnemyCardEngineEffect = ""
              }
          }
          this.countPoints()
      }
      },
      chooseEnemyCard(cardBase, baseI){
          if(this.playerPassed && this.playerScore - this.opponentScore < 4){
            for(let i = 0; i < this.opponentHand.length; i++){
                if(this.opponentHand[i].cardRarity=="Bronze"){return i}
            }
          }
          let controlCards = []
          let supportCards = []
          let engines = []
          let graveCards = []
          let removalCards = []
          let miscCards = []
          let portalI = null
          let enginesInDeck = []
          for (let i = 0; i < baseI.length; i++){
              if((cardBase[baseI[i]].cardEffect=="Damage" || cardBase[baseI[i]].cardEffect=="Adjacent Damage" || cardBase[baseI[i]].cardEffect=="Trade Place" || cardBase[baseI[i]].cardStatus=="Bleeding" || cardBase[baseI[i]].cardStatus=="Adjacent Bleeding" || cardBase[baseI[i]].cardStatus=="Freeze") && (cardBase[baseI[i]].cardTargetUnitType != "Ally" && cardBase[baseI[i]].cardEffectTarget!="Random")){controlCards.push(baseI[i])}
              else if((cardBase[baseI[i]].cardEffect=="Boost" || cardBase[baseI[i]].cardStatus=="Vitality" || cardBase[baseI[i]].cardStatus=="Shield" || cardBase[baseI[i]].cardEffect=="Damage Bond" || cardBase[baseI[i]].cardEffect=="Unkillable") && (cardBase[baseI[i]].cardTargetUnitType!="Enemy" || cardBase[baseI[i]].cardTargetUnitType!="Self")){supportCards.push(baseI[i])}
              else if((cardBase[baseI[i]].cardEffect=="Engine" || cardBase[baseI[i]].cardEffect2=="Engine") && (cardBase[baseI[i]].cardEngineType!="Boost" || cardBase[baseI[i]].cardTargetUnitType!="Enemy")){engines.push(baseI[i])}
              else if(cardBase[baseI[i]].cardEffect=="Copy Grave Unit" || cardBase[baseI[i]].cardEffect=="Grave Consume"){graveCards.push(baseI[i])}
              else if(cardBase[baseI[i]].cardEffect=="Removal"){removalCards.push(baseI[i])}
              else if(cardBase[baseI[i]].playedCard=="Any Card From Own Deck"){portalI = baseI[i]; miscCards.push(baseI[i])}
              else {miscCards.push(baseI[i])}
          }
          for(let i = 0; i < this.opponentDeck.length; i++){if((this.opponentDeck[i].cardEffect=="Engine" || this.opponentDeck[i].cardEffect2=="Engine") && (this.opponentDeck[i].cardEngineType!="Boost" || this.opponentDeck[i].cardTargetUnitType!="Enemy")){enginesInDeck.push(i)}}
          let removalPossible = false
          let areBleedingEnemies = false
          let areTallEnemies = false
          let haveBleedRemoval = false
          let haveTallRemoval = false
          let tallRemovalValue = null
          for(let i = 0; i < removalCards.length; i++){
              if(cardBase[removalCards[i]].cardRemovalCondition=="Bleeding Enemy Health"){haveBleedRemoval=true}
              if(cardBase[removalCards[i]].cardRemovalConditionValue){haveTallRemoval=true; tallRemovalValue = cardBase[removalCards[i]].cardRemovalConditionValue}
          }
          for(let i = 0; i < this.filledBoardSpace.length; i++){
              if(this.playerBoard[this.filledBoardSpace[i]].statusses[0].status && haveBleedRemoval){areBleedingEnemies=true; removalPossible=true}
              if(this.playerBoard[this.filledBoardSpace[i]].cardHealth>tallRemovalValue && haveTallRemoval){areTallEnemies=true; removalPossible=true}
          }
          if (engines.length){
              this.chosenEnemyCardType = "Engine"
              let goldEngines = []
              let silverEngines = []
              for(let i = 0; i < engines.length; i++){
                  if(cardBase[engines[i]].cardEngineCondition=="Alone" && this.filledOpponentBoardSpace.length==0){return engines[i]} 
                  else if(cardBase[engines[i]].cardRarity=="Gold" && cardBase[engines[i]].cardEffectTarget!="All Enemies"){goldEngines.push(engines[i])}
                  else if(cardBase[engines[i]].cardRarity=="Silver"){silverEngines.push(engines[i])}
              }
              if(goldEngines.length){return goldEngines[Math.floor(Math.random()*goldEngines.length)]}
              else if(silverEngines.length){return silverEngines[Math.floor(Math.random()*silverEngines.length)]}
              else {return engines[Math.floor(Math.random()*engines.length)]}
        } if (portalI != null && enginesInDeck.length){
                return portalI;
        } if (supportCards.length && this.opponentEngines.length){
              this.chosenEnemyCardType = "Support"
              let prioritySupport = []
              let goodSupport = []
              for(let i = 0; i < supportCards.length; i++){
                  if(cardBase[supportCards[i]].cardEffect=="Unkillable"){return supportCards[i]}
                  else if(cardBase[supportCards[i]].cardStatus=="Vitality"){prioritySupport.push(supportCards[i])}
                  else if(cardBase[supportCards[i]].cardEffect=="Damage Bond" || cardBase[supportCards[i]].cardStatus=="Shield"){goodSupport.push(supportCards[i])}
              }
              if(prioritySupport.length){return prioritySupport[Math.floor(Math.random()*prioritySupport.length)]}
              else if(goodSupport.length){return goodSupport[Math.floor(Math.random()*goodSupport.length)]}
              else {return supportCards[Math.floor(Math.random()*supportCards.length)]}
        } if (controlCards.length && this.alliedEngines.length){
              this.chosenEnemyCardType = "Control"
              let priorityControl = []
              let goodControl = []
              for(let i = 0; i < controlCards.length; i++){
                  if(cardBase[controlCards[i]].cardEffect=="Trade Place"){return controlCards[i]}
                  else if(cardBase[controlCards[i]].cardStatus=="Freeze"){priorityControl.push(controlCards[i])}
                  else if(cardBase[controlCards[i]].cardEffect=="Bleeding"){goodControl.push(controlCards[i])}
              }
              if(priorityControl.length){return priorityControl[Math.floor(Math.random()*priorityControl.length)]}
              else if(goodControl.length){return goodControl[Math.floor(Math.random()*goodControl.length)]}
              else {return controlCards[Math.floor(Math.random()*controlCards.length)]}
        } if (removalCards.length && removalPossible){
            this.chosenEnemyCardType = "Removal"
            for(let i = 0; i < removalCards.length; i++){
                if(cardBase[removalCards[i]].cardRemovalCondition=="Above Value" && areTallEnemies){return removalCards[i]}
                else if (cardBase[removalCards[i]].cardRemovalCondition=="Bleeding Enemy Health" && areBleedingEnemies){return removalCards[i]}
            }
        } 
        for(let i = 0; i < baseI.length; i++){if(cardBase[baseI[i]].cardRarity=="Gold"){return baseI[i]}}
        console.log("Random card chosen")
        return baseI[Math.floor(Math.random()*baseI.length)] 
      },
      chooseEnemyCardPosition(availableSpace){
          let boostedSpots = []
          let selfDamageSpots = []
          let boostConEngine = []
          let protector = []
          let engines = []
          let adjacentSpot = null
          let highestHP = 0
          let highestHPI = null
          let goodSpace
          let board = this.filledOpponentBoardSpace.sort(function(a, b){return a-b});
          for(let i = 0; i<board.length; i++){
              if(i>0){if(board[i]-board[i-1]==2 && this.opponentBoard[board[i]-1].cardName!=true){adjacentSpot=board[i]-1}}
              if(this.opponentBoard[board[i]].cardEngineType=="Boost" && (this.opponentBoard[board[i]].cardEngineTarget=="Left" || this.opponentBoard[board[i]].cardEngineTarget=="Adjacent") && board[i]!=0 && this.opponentBoard[board[i]-1].cardName==undefined){boostedSpots.push(board[i]-1)}
              if(this.opponentBoard[board[i]].cardEngineType=="Boost" && (this.opponentBoard[board[i]].cardEngineTarget=="Right" || this.opponentBoard[board[i]].cardEngineTarget=="Adjacent") && board[i]!=9 && this.opponentBoard[board[i]+1].cardName==undefined){boostedSpots.push(board[i]+1)}
              if(this.opponentBoard[board[i]].cardEngineType=="Damage" && (this.opponentBoard[board[i]].cardEngineTarget=="Left" || this.opponentBoard[board[i]].cardEngineTarget=="Adjacent") && board[i]!=0 && this.opponentBoard[board[i]-1].cardName==undefined){selfDamageSpots.push(board[i]-1)}
              if(this.opponentBoard[board[i]].cardEngineType=="Damage" && (this.opponentBoard[board[i]].cardEngineTarget=="Right" || this.opponentBoard[board[i]].cardEngineTarget=="Adjacent") && board[i]!=9 && this.opponentBoard[board[i]+1].cardName==undefined){selfDamageSpots.push(board[i]+1)}
              if(this.opponentBoard[board[i]].cardEngineCondition=="Received Boost"){boostConEngine.push(board[i])}
              if(this.opponentBoard[board[i]].cardEffect=="Unkillable" && board[i]!=0){protector.push([board[i]])}
              if(this.opponentBoard[board[i]].cardEffect=="Engines"){engines.push(board[i])}
              if(this.opponentBoard[board[i]].cardHealth>highestHP && board[i]>0){highestHP = this.opponentBoard[board[i]].cardHealth; highestHPI=board[i]}
          }
          if(this.chosenEnemyCardType=="Engine"){
              if(this.chosenEnemyPlayableCard.cardEngineType=="Boost" && this.chosenEnemyPlayableCard.cardEngineTarget!="Self"){
                  if(this.chosenEnemyPlayableCard.cardEngineTarget=="Left"){
                      if(availableSpace.length>1 && availableSpace.includes(0)){availableSpace.shift()}
                      if(boostConEngine.length && boostConEngine[0]<9){if(this.opponentBoard[boostConEngine[0]+1].cardName==undefined){return boostConEngine[0]+1}}
                      if(boostConEngine.length && boostConEngine[1]<9){if(this.opponentBoard[boostConEngine[1]+1].cardName==undefined){return boostConEngine[1]+1}}
                      for(let i = 0; i<board.length; i++){if(board[i]!=9){if(this.opponentBoard[board[i]+1].cardName==undefined){return board[i]+1}}}
                      return availableSpace[Math.floor(Math.random()*availableSpace.length)]
                } else if(this.chosenEnemyPlayableCard.cardEngineTarget=="Right"){
                      if(availableSpace.length>1 && availableSpace.includes(9)){availableSpace.pop()}
                      if(boostConEngine.length && boostConEngine[0]>0){if(this.opponentBoard[boostConEngine[0]-1].cardName==undefined){return boostConEngine[0]-1}}
                      if(boostConEngine.length && boostConEngine[1]>0){if(this.opponentBoard[boostConEngine[1]-1].cardName==undefined){return boostConEngine[1]-1}}
                      for(let i = 0; i<board.length; i++){if(board[i]!=0){if(this.opponentBoard[board[i]-1].cardName==undefined){return board[i]-1}}}
                      return availableSpace[Math.floor(Math.random()*availableSpace.length)]
                } else if(this.chosenEnemyPlayableCard.cardEngineTarget=="Adjacent"){
                      if(availableSpace.length>1 && availableSpace.includes(0)){availableSpace.shift()}
                      if(availableSpace.length>1 && availableSpace.includes(9)){availableSpace.pop()}
                      if(adjacentSpot!=null){return adjacentSpot}
                      for(let i = 0; i<board.length; i++){if(board[i]!=0){if(this.opponentBoard[board[i]-1].cardName==undefined){return board[i]-1}}}
                      for(let i = 0; i<board.length; i++){if(board[i]!=9){if(this.opponentBoard[board[i]+1].cardName==undefined){return board[i]+1}}}
                      return availableSpace[Math.floor(Math.random()*availableSpace.length)]
                }
            } else if(this.chosenEnemyPlayableCard.cardEngineCondition=="Received Boost"){
                if(availableSpace.length>1 && availableSpace.includes(0)){availableSpace.shift()}
                if(availableSpace.length>1 && availableSpace.includes(9)){availableSpace.pop()}
                if(boostedSpots.length){goodSpace = boostedSpots[Math.floor(Math.random()*boostedSpots.length)]; if(this.opponentBoard[goodSpace].cardName==undefined){return goodSpace}}
                return availableSpace[Math.floor(Math.random()*availableSpace.length)]
            } else if(this.chosenEnemyPlayableCard.cardEngineType=="Damage" && this.chosenEnemyPlayableCard.cardEngineTarget!="Random"){
                if(this.chosenEnemyPlayableCard.cardEngineTarget=="Left"){
                      if(availableSpace.length>1 && availableSpace.includes(0)){availableSpace.shift()}
                      for(let i = 0; i<board.length; i++){if(board[i]!=9){if(this.opponentBoard[board[i]+1].cardName==undefined){return board[i]+1}}}
                      return availableSpace[Math.floor(Math.random()*availableSpace.length)]
                } else if(this.chosenEnemyPlayableCard.cardEngineTarget=="Right"){
                      if(availableSpace.length>1 && availableSpace.includes(9)){availableSpace.pop()}
                      if(protector.length && protector[0]>1 && this.opponentBoard[protector[0]-2].cardName==undefined){return protector[0]-2}
                      if(protector.length && protector[1]>1 && this.opponentBoard[protector[1]-2].cardName==undefined){return protector[1]-2}
                      for(let i = 0; i<board.length; i++){if(board[i]!=0){if(this.opponentBoard[board[i]-1].cardName==undefined){return board[i]-1}}}
                      return availableSpace[Math.floor(Math.random()*availableSpace.length)]
                } else if(this.chosenEnemyPlayableCard.cardEngineTarget=="Adjacent"){
                      if(availableSpace.length>1 && availableSpace.includes(0)){availableSpace.shift()}
                      if(availableSpace.length>1 && availableSpace.includes(9)){availableSpace.pop()}
                      if(adjacentSpot!=null){return adjacentSpot}
                      if(protector.length && protector[0]>1 && this.opponentBoard[protector[0]-2].cardName==undefined){return protector[0]-2}
                      if(protector.length && protector[1]>1 && this.opponentBoard[protector[1]-2].cardName==undefined){return protector[1]-2}
                      for(let i = 0; i<board.length; i++){if(board[i]!=0){if(this.opponentBoard[board[i]-1].cardName==undefined){return board[i]-1}}}
                      for(let i = 0; i<board.length; i++){if(board[i]!=9){if(this.opponentBoard[board[i]+1].cardName==undefined){return board[i]+1}}}
                      return availableSpace[Math.floor(Math.random()*availableSpace.length)]
                }
            } else {
                let goodEngineSpots = availableSpace.filter((el) => !selfDamageSpots.includes(el));
                if(protector.length){return protector[Math.floor(Math.random()*protector.length)]-1}
                if(boostedSpots.length){let goodSpace = boostedSpots[Math.floor(Math.random()*boostedSpots.length)]; if(this.opponentBoard[goodSpace].cardName==undefined){return goodSpace}}
                if(goodEngineSpots.length){return goodEngineSpots[Math.floor(Math.random()*goodEngineSpots.length)]}
                return availableSpace[Math.floor(Math.random()*availableSpace.length)]
            }   
        } if(this.chosenEnemyCardType=="Support"){
              if(this.chosenEnemyPlayableCard.cardEffectTarget=="Left"){
                      if(availableSpace.length>1 && availableSpace.includes(0)){availableSpace.shift()}
                      for(let i = 0; i<engines.length; i++){if(engines[i]!=9){if(this.opponentBoard[engines[i]+1].cardName==undefined){return engines[i]+1}}}
                      for(let i = 0; i<board.length; i++){if(board[i]!=9){if(this.opponentBoard[board[i]+1].cardName==undefined){return board[i]+1}}}
                      return availableSpace[Math.floor(Math.random()*availableSpace.length)]
            } else if(this.chosenEnemyPlayableCard.cardEffectTarget=="Right"){
                      if(availableSpace.length>1 && availableSpace.includes(9)){availableSpace.pop()}
                      for(let i = 0; i<engines.length; i++){if(engines[i]!=0){if(this.opponentBoard[engines[i]-1].cardName==undefined){return engines[i]-1}}}
                      for(let i = 0; i<board.length; i++){if(board[i]!=0){if(this.opponentBoard[board[i]-1].cardName==undefined){return board[i]-1}}}
                      return availableSpace[Math.floor(Math.random()*availableSpace.length)]
            } else if(this.chosenEnemyPlayableCard.cardEffectTarget=="Adjacent"){
                      if(availableSpace.length>1 && availableSpace.includes(0)){availableSpace.shift()}
                      if(availableSpace.length>1 && availableSpace.includes(9)){availableSpace.pop()}
                      if(adjacentSpot!=null){return adjacentSpot}
                      for(let i = 0; i<engines.length; i++){if(engines[i]!=0){if(this.opponentBoard[engines[i]-1].cardName==undefined){return engines[i]-1}}}
                      for(let i = 0; i<engines.length; i++){if(engines[i]!=9){if(this.opponentBoard[engines[i]+1].cardName==undefined){return engines[i]+1}}}
                      for(let i = 0; i<board.length; i++){if(board[i]!=0){if(this.opponentBoard[board[i]-1].cardName==undefined){return board[i]-1}}}
                      for(let i = 0; i<board.length; i++){if(board[i]!=9){if(this.opponentBoard[board[i]+1].cardName==undefined){return board[i]+1}}}
                      return availableSpace[Math.floor(Math.random()*availableSpace.length)]
            } else {
                      return availableSpace[Math.floor(Math.random()*availableSpace.length)]
            }
        } if(this.chosenEnemyCardType=="Negative Effect"){
            let goodSpots = availableSpace.filter((el) => !selfDamageSpots.includes(el));
            if(goodSpots.length){return goodSpots[Math.floor(Math.random()*goodSpots.length)]}
            return availableSpace[Math.floor(Math.random()*availableSpace.length)]
        } if(this.chosenEnemyPlayableCard.cardEffectCondition=="Right Unit Health"){
            if(highestHPI!=null){return highestHPI-1}
            else {
                  let highestHP2 = 0
                  let highestHPI2 = null
                  let availablePos = [] 
                  for(let i = 1; i < board.length; i++){if(board[i]!=board[i-1]+1){availablePos.push(board[i]-1)}}
                  if(availablePos.length){for(let i = 0; i < availablePos.length; i++){if(this.opponentBoard[availablePos[0]+1].cardHealth > highestHP2){highestHP2 = this.opponentBoard[availablePos[0]+1].cardHealth; highestHPI2 = availablePos[0]+1}}}
                  if(highestHPI2 != null){return highestHPI2-1}
            }
        }
        if(boostedSpots.length){return boostedSpots[Math.floor(Math.random()*boostedSpots.length)]}
        if(selfDamageSpots.length){return selfDamageSpots[Math.floor(Math.random()*selfDamageSpots.length)]}
        if(protector.length && protector[0] && this.opponentBoard[protector[0]-1].cardName==undefined){return protector[0]-1}
        if(protector.length && protector[1] && this.opponentBoard[protector[0]-1].cardName==undefined){return protector[1]-1}
        return availableSpace[Math.floor(Math.random()*availableSpace.length)]
        
      },
      processEnemyDeploy(){
          let oppPositiveI = null
          let oppNegativeI = null
          let playerPositiveI = null
          let playerNegativeI = null
          let i = null
          let opponentNonEngines = []
          for(let i = 0; i < this.opponentBoard.length; i++){
            if(this.opponentBoard[i].cardEffect != "Engine" && this.opponentBoard[i].cardEffect2 != "Engine"){
              opponentNonEngines.push([this.opponentBoard[i], i])
            }}
          let alliedNonEngines = []
          for(let i = 0; i < this.playerBoard.length; i++){
            if(this.playerBoard[i].cardEffect != "Engine" && this.playerBoard[i].cardEffect2 != "Engine"){
              alliedNonEngines.push([this.playerBoard[i], i])
            }
            }  
          if(this.opponentEngines.length>0 && opponentNonEngines.length){
              let smallestHP = 99999999  
              let highestHP = 0
              for (let i = 0; i < this.opponentEngines.length; i++){
                if(this.opponentEngines[i][0].cardHealth<smallestHP){
                  smallestHP = this.opponentEngines[i][0].cardHealth
                  oppPositiveI = this.opponentEngines[i][1]
                }
              }
              for(let i = 0; i < opponentNonEngines.length; i++){  
                if(opponentNonEngines[i][0].cardHealth>highestHP){
                  highestHP = opponentNonEngines[i][0].cardHealth
                  oppNegativeI = opponentNonEngines[i][1]
                } 
            } 
        } else {
              let smallestHP = 99999999  
              let highestHP = 0
              for (let i = 0; i < this.filledOpponentBoardSpace.length; i++){
                if(this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth<smallestHP){
                  smallestHP = this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth
                  oppPositiveI = this.filledOpponentBoardSpace[i]
              }
              }
              for (let i = 0; i < this.filledOpponentBoardSpace.length; i++){
                if(this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth>highestHP){
                  highestHP = this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth
                  oppNegativeI = this.filledOpponentBoardSpace[i]
                  }
              }
        } 
          if(this.alliedEngines.length>0 && alliedNonEngines.length){
              let smallestHP = 99999999  
              let highestHP = 0
              for (let i = 0; i < this.alliedEngines.length; i++){
                if(this.alliedEngines[i][0].cardHealth<smallestHP){
                  smallestHP = this.alliedEngines[i][0].cardHealth
                  playerNegativeI = this.alliedEngines[i][1]
                }
              }
              for(let i = 0; i < alliedNonEngines.length; i++){  
                if(alliedNonEngines[i][0].cardHealth>highestHP){
                  highestHP = alliedNonEngines[i][0].cardHealth
                  playerPositiveI = alliedNonEngines[i][1]
                }
              }
        } else {
              let smallestHP = 99999999  
              let highestHP = 0
              for (let i = 0; i < this.filledBoardSpace.length; i++){
                if(this.playerBoard[this.filledBoardSpace[i]].cardHealth<smallestHP){
                  smallestHP = this.playerBoard[this.filledBoardSpace[i]].cardHealth
                  playerNegativeI = this.filledBoardSpace[i]
              }
              }
              for (let i = 0; i < this.filledBoardSpace.length; i++){
                if(this.playerBoard[this.filledBoardSpace[i]].cardHealth>highestHP){
                  highestHP = this.playerBoard[this.filledBoardSpace[i]].cardHealth
                  playerPositiveI = this.filledBoardSpace[i]
                  }
              }
        } 
          console.log(`oppPos: ${oppPositiveI}, oppNeg: ${oppNegativeI}, playerPos: ${playerPositiveI}, playerNeg: ${playerNegativeI}, boardSpace: ${this.filledBoardSpace}`)
          if(oppPositiveI==null){oppPositiveI=this.filledOpponentBoardSpace[Math.floor(Math.random()*this.filledOpponentBoardSpace.length)]}
          if(oppNegativeI==null){oppNegativeI=this.filledOpponentBoardSpace[Math.floor(Math.random()*this.filledOpponentBoardSpace.length)]}
          if(playerPositiveI==null){playerPositiveI=this.filledBoardSpace[Math.floor(Math.random()*this.filledBoardSpace.length)]}
          if(playerNegativeI==null){playerNegativeI=this.filledBoardSpace[Math.floor(Math.random()*this.filledBoardSpace.length)]}
          if(this.chosenEnemyCardEffectCondition=="Right Unit Health"){
              if(this.chosenEnemyCardIndex!=9){if(this.opponentBoard[this.chosenEnemyCardIndex + 1].cardName){this.chosenEnemyCardEffectValue=this.opponentBoard[this.chosenEnemyCardIndex + 1].cardHealth}}
          }
          if(this.chosenEnemyCardEffectCondition=="Twice The Number Of Cards In Deck"){
            this.chosenEnemyCardEffectValue = this.opponentDeck.length * 2
          }
          if(this.chosenEnemyCardTargetType=="Ally" && this.filledOpponentBoardSpace.length){
              if(this.chosenEnemyCardEffect=="Boost"){
                  i = oppPositiveI
                  this.opponentBoard[i].cardHealth += this.chosenEnemyCardEffectValue
                  if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.chosenEnemyCardEffectValue}
                  if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.chosenEnemyCardEffectValue}
                  if(this.opponentBoard[i].cardEngineCondition){if(this.opponentBoard[i].cardEngineCondition=="Received Boost"){this.opponentBoard[i].cardEngineValue++}}
            } if(this.chosenEnemyCardEffect=="Damage"){
                i = oppNegativeI
                    if(this.opponentBoard[i].damageBondI){
                        if(i!=9){if(this.opponentBoard[i+1].cardEffect!="Unkillable"){this.opponentBoard[this.opponentBoard[this.opponentBoard[i]].damageBondI].cardHealth -= this.chosenEnemyCardEffectValue}}
                        else{this.opponentBoard[this.opponentBoard[this.opponentBoard[i]].damageBondI].cardHealth -= this.chosenEnemyCardEffectValue}
                        if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                        if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}
                  } else if(this.opponentBoard[i].statusses[2].status=="Shield"){
                      this.opponentBoard[i].statusses[2]={}
                  } else {
                      this.opponentBoard[i].cardHealth -= this.chosenEnemyCardEffectValue
                      if(this.opponentBoard[i].cardEngineCondition=="Damage Taken"){this.opponentBoard[i].cardEngineValue++}
                    }
            } if(this.chosenEnemyCardEffect=="Status"){
                let duration = 0
                if(this.chosenEnemyCardStatusDuration){duration = this.chosenEnemyCardStatusDuration}
                  if(this.chosenEnemyCardStatus=="Bleeding") {
                      i = oppNegativeI
                      if(this.opponentBoard[i].statusses[0].duration && this.opponentBoard[i].statusses[0].duration>0){
                        duration = this.chosenEnemyCardStatusDuration + this.opponentBoard[i].statusses[0].duration}   
                      this.opponentBoard[i].statusses[0] = {status: this.chosenEnemyCardStatus, duration}
                      if(this.chosenEnemyCardStatusDuration){duration = this.chosenEnemyCardStatusDuration}
                } if(this.chosenEnemyCardStatus=="Adjacent Bleeding") {
                      i = oppNegativeI
                          if(this.opponentBoard[i].statusses[0].duration && this.opponentBoard[i].statusses[0].duration>0){
                            duration = this.chosenEnemyCardStatusDuration + this.opponentBoard[i].statusses[0].duration}   
                          this.opponentBoard[i].statusses[0] = {status: "Bleeding", duration}
                          if(this.chosenEnemyCardStatusDuration){duration = this.chosenEnemyCardStatusDuration}
                        if(i!=0){if(this.opponentBoard[i-1].cardName) {
                          if(this.opponentBoard[i-1].statusses[0].duration && this.opponentBoard[i-1].statusses[0].duration>0){
                            duration = this.chosenEnemyCardStatusDuration + this.opponentBoard[i-1].statusses[0].duration}   
                          this.opponentBoard[i-1].statusses[0] = {status: "Bleeding", duration}
                          if(this.chosenEnemyCardStatusDuration){duration = this.chosenEnemyCardStatusDuration}
                     }} if(i!=9){if(this.opponentBoard[i+1].cardName) {
                          if(this.opponentBoard[i+1].statusses[0].duration && this.opponentBoard[i+1].statusses[0].duration>0){
                            duration = this.chosenEnemyCardStatusDuration + this.opponentBoard[i+1].statusses[0].duration}   
                          this.opponentBoard[i+1].statusses[0] = {status: "Bleeding", duration}
                          if(this.chosenEnemyCardStatusDuration){duration = this.chosenEnemyCardStatusDuration}
                     }}
                } if(this.chosenEnemyCardStatus=="Vitality"){
                    i = oppPositiveI
                    if(this.opponentBoard[i].statusses[1].duration && this.opponentBoard[i].statusses[1].duration>0){
                        duration = this.chosenEnemyCardStatusDuration + this.opponentBoard[i].statusses[1].duration}   
                    this.opponentBoard[i].statusses[1] = {status: this.chosenEnemyCardStatus, duration}
                } if(this.chosenEnemyCardStatus=="Shield"){i = oppPositiveI; this.opponentBoard[i].statusses[2] = {status: this.chosenEnemyCardStatus, duration: 999}}
                  if(this.chosenEnemyCardStatus=="Freeze"){i = oppNegativeI; this.opponentBoard[i].statusses[3] = {status: this.chosenEnemyCardStatus, duration: 999}}
            } if(this.chosenEnemyCardEffect=="Damage Bond"){
                i = oppPositiveI
                this.opponentBoard[i].damageBondI = this.chosenEnemyCardIndex
            } if(this.chosenEnemyCardEffect=="Consume"){
                i = oppNegativeI
                this.opponentBoard[this.filledOpponentBoardSpace[this.filledOpponentBoardSpace.length-1]].cardHealth += this.opponentBoard[i].cardHealth
                if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentBoard[i].cardHealth}
                if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentBoard[i].cardHealth}
                this.opponentBoard[i].cardHealth=0
            }
        } else if(this.chosenEnemyCardTargetType=="Enemy" && this.filledBoardSpace.length){
              if(this.chosenEnemyCardEffect=="Boost"){
                  i = playerPositiveI
                  this.playerBoard[i].cardHealth += this.chosenEnemyCardEffectValue
                  if(this.oppSpyI!=null){this.opponentBoard[this.oppSpyI].cardHealth += this.chosenEnemyCardEffectValue}
                  if(this.oppSpyI2!=null){this.opponentBoard[this.oppSpyI2].cardHealth += this.chosenEnemyCardEffectValue}
                  if(this.playerBoard[i].cardEngineCondition){if(this.playerBoard[i].cardEngineCondition=="Received Boost"){this.playerBoard[i].cardEngineValue++}}
       } else if(this.chosenEnemyCardEffect=="Damage"){
                  i = playerNegativeI
                    if(this.playerBoard[i].damageBondI){
                        this.playerBoard[this.playerBoard[this.playerBoard[i]].damageBondI].cardHealth -= this.chosenEnemyCardEffectValue
                  } else if(this.playerBoard[i].statusses[2].status=="Shield"){
                      this.playerBoard[i].statusses[2]={}
                  } else {
                      if(i!=9){if(this.playerBoard[i+1].cardEffect!="Unkillable"){this.playerBoard[i].cardHealth -= this.chosenEnemyCardEffectValue}}
                      else{this.playerBoard[i].cardHealth -= this.chosenEnemyCardEffectValue}
                      if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                      if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}
                      if(this.playerBoard[i].cardEngineCondition){if(this.playerBoard[i].cardEngineCondition=="Damage Taken"){this.playerBoard[i].cardEngineValue++}}
                  }
       } else if(this.chosenEnemyCardEffect=="Adjacent Damage"){
                    i = playerNegativeI
                    if(this.playerBoard[i].damageBondI){
                        this.playerBoard[this.playerBoard[this.playerBoard[i]].damageBondI].cardHealth -= this.chosenEnemyCardEffectValue
                  } else if(this.playerBoard[i].statusses[2].status=="Shield"){
                      this.playerBoard[i].statusses[2]={}
                  } else {
                      if(this.playerBoard[i+1].cardEffect!="Unkillable"){this.playerBoard[i].cardHealth -= this.chosenEnemyCardEffectValue}
                      if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                      if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}
                      if(this.playerBoard[i].cardEngineCondition=="Damage Taken"){this.playerBoard[i].cardEngineValue++}
                  }
                if(i!=0){if(this.playerBoard[i-1].cardName){
                      if(this.playerBoard[i-1].damageBondI){
                        this.playerBoard[this.playerBoard[this.playerBoard[i-1]].damageBondI].cardHealth -= this.chosenEnemyCardEffectValue
                  } else if(this.playerBoard[i-1].statusses[2].status=="Shield"){
                      this.playerBoard[i-1].statusses[2]={}
                  } else {
                      if(this.playerBoard[i].cardEffect!="Unkillable"){this.playerBoard[i-1].cardHealth -= this.chosenEnemyCardEffectValue}
                      if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                      if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}
                      if(this.playerBoard[i-1].cardEngineCondition=="Damage Taken"){this.playerBoard[i-1].cardEngineValue++}
                  }
                }}
                if(i!=9){if(this.playerBoard[i+1].cardName){
                      if(this.playerBoard[i+1].damageBondI){
                        this.playerBoard[this.playerBoard[this.playerBoard[i+1]].damageBondI].cardHealth -= this.chosenEnemyCardEffectValue
                  } else if(this.playerBoard[i+1].statusses[2].status=="Shield"){
                      this.playerBoard[i+1].statusses[2]={}
                  } else {
                      if(this.playerBoard[i+2].cardEffect!="Unkillable"){this.playerBoard[i+1].cardHealth -= this.chosenEnemyCardEffectValue}
                      if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                      if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}
                      if(this.playerBoard[i+1].cardEngineCondition=="Damage Taken"){this.playerBoard[i+1].cardEngineValue++}
                  }
                }}
       } else if(this.chosenEnemyCardEffect=="Status"){
                let duration = 0
                if(this.chosenEnemyCardStatusDuration){duration = this.chosenEnemyCardStatusDuration}
                  if(this.chosenEnemyCardStatus=="Bleeding") {
                      i = playerNegativeI
                      if(this.playerBoard[i].statusses[0].duration && this.playerBoard[i].statusses[0].duration>0){
                        duration = this.chosenEnemyCardStatusDuration + this.playerBoard[i].statusses[0].duration}   
                      this.playerBoard[i].statusses[0] = {status: this.chosenEnemyCardStatus, duration}
                      if(this.chosenEnemyCardStatusDuration){duration = this.chosenEnemyCardStatusDuration}
                } if(this.chosenEnemyCardStatus=="Adjacent Bleeding") {
                      i = playerNegativeI
                      if(this.playerBoard[i].statusses[0].duration && this.playerBoard[i].statusses[0].duration>0){
                        duration = this.chosenEnemyCardStatusDuration + this.playerBoard[i].statusses[0].duration}   
                      this.playerBoard[i].statusses[0] = {status: "Bleeding", duration}
                      if(this.chosenEnemyCardStatusDuration){duration = this.chosenEnemyCardStatusDuration}
                      if(i!=0){if(this.playerBoard[i-1].cardName) {
                        if(this.playerBoard[i-1].statusses[0].duration && this.playerBoard[i-1].statusses[0].duration>0){
                          duration = this.chosenEnemyCardStatusDuration + this.playerBoard[i-1].statusses[0].duration}   
                        this.playerBoard[i-1].statusses[0] = {status: "Bleeding", duration}
                        if(this.chosenEnemyCardStatusDuration){duration = this.chosenEnemyCardStatusDuration}
                   }} if(i!=9){if(this.playerBoard[i+1].cardName) {
                        if(this.playerBoard[i+1].statusses[0].duration && this.playerBoard[i+1].statusses[0].duration>0){
                          duration = this.chosenEnemyCardStatusDuration + this.playerBoard[i+1].statusses[0].duration}   
                        this.playerBoard[i+1].statusses[0] = {status: "Bleeding", duration}
                        if(this.chosenEnemyCardStatusDuration){duration = this.chosenEnemyCardStatusDuration}
                   }}
                } if(this.chosenEnemyCardStatus=="Vitality"){
                    i = playerPositiveI
                    if(this.playerBoard[i].statusses[1].duration && this.playerBoard[i].statusses[1].duration>0){
                        duration = this.chosenEnemyCardStatusDuration + this.playerBoard[i].statusses[1].duration}   
                    this.playerBoard[i].statusses[1] = {status: this.chosenEnemyCardStatus, duration}
                } if(this.chosenEnemyCardStatus=="Shield"){i = playerPositiveI; this.playerBoard[i].statusses[2] = {status: this.chosenEnemyCardStatus, duration: 999}}
                  if(this.chosenEnemyCardStatus=="Freeze"){i = playerNegativeI; this.playerBoard[i].statusses[3] = {status: this.chosenEnemyCardStatus, duration: 999}}
       } else if(this.chosenEnemyCardEffect=="Trade Place"){
             i = playerPositiveI
        if(this.playerBoard[i].cardEffect=="Engine" || this.playerBoard[i].cardEffect2=="Engine"){
           if(this.chiefI==i){this.chiefI=null}
      else if(this.chiefI2==i){this.chiefI2=null}
           if(this.spyI==i){this.spyI=null}
      else if(this.spyI2==i){this.spyI2=null}
           if(this.playerBoard[i].cardEngineCondition=="Allied Unit Damaged" && this.oppChiefI!=null){this.oppChiefI2=this.chosenEnemyCardIndex}
      else if(this.playerBoard[i].cardEngineCondition=="Allied Unit Damaged"){this.oppChiefI=this.chosenEnemyCardIndex}
           if(this.playerBoard[i].cardEngineCondition=="Enemy Boosted" && this.oppSpyI!=null){this.oppSpyI2=this.chosenEnemyCardIndex}
      else if(this.playerBoard[i].cardEngineCondition=="Enemy Boosted"){this.oppSpyI=this.chosenEnemyCardIndex}
           for(let o = 0; o < this.alliedEngines.length; o++){
               if(this.alliedEngines[o][1]==i){
                   let engine = this.alliedEngines.splice(o, 1);
                   this.opponentEngines.push(engine)}
           }
       }
           let playerTrade = this.opponentBoard[this.chosenEnemyCardIndex]
           let opponentTrade = this.playerBoard[i]
           this.opponentBoard[this.chosenEnemyCardIndex] = opponentTrade
           this.playerBoard[i] = playerTrade
       } else if(this.chosenEnemyCardEffect=="Removal"){
           if(this.chosenEnemyCardRemovalCondition){
               if(this.chosenEnemyCardRemovalCondition=="Above Value"){
                   let i = null
                   let highestHP = 0
                   let removableUnits = []
                   for(let i = 0; i < this.playerBoard.length; i++){
                       if (this.playerBoard[i].cardHealth > this.chosenEnemyCardRemovalConditionValue){
                           removableUnits.push([this.playerBoard[i], i])
                       }}
                    if(removableUnits.length){ 
                      for(let o = 0; o < removableUnits.length; o++){
                          if(removableUnits[o][0].cardHealth>highestHP){
                              highestHP = removableUnits[o][0].cardHealth
                              i = removableUnits[o][1]
                          }
                      }   
                    } else {return "aaa"}
                    this.playerBoard[i].cardHealth = 0
            }} else if(this.chosenEnemyCardRemovalCondition=="Bleeding Enemy Health"){
                    let i = null
                    let highestHP = 0
                    let removableUnits = []
                    for(let i = 0; i < this.playerBoard.length; i++){
                      if(this.playerBoard[i].statusses[0].duration){
                           removableUnits.push([this.playerBoard[i], i])
                      }}
                    if(removableUnits.length){ 
                      for(let i = 0; i < removableUnits.length; i++){
                          if(removableUnits[i][0].cardHealth>highestHP){
                              highestHP = removableUnits[i][0].cardHealth
                              i = removableUnits[i][1]
                          }
                      }   
                    } else{return "aaa"}
                    this.opponentBoard[this.chosenEnemyCardIndex].cardHealth += this.playerBoard[i].cardHealth
                    this.playerBoard[i].cardHealth = 0   
            
           }
       }
       }
      },
      processEngines(){
         for(let i=0; i < this.alliedEngines.length; i++){
            setTimeout(() => { 
            let pass = true
            if(this.alliedEngines[i][0].cardEngineCondition=="Number Of Enemy Units With Bleeding"){
                let value = 0
                for(let o = 0; o < 10; o++){
                    if(this.opponentBoard[o].cardName!=null){if(this.opponentBoard[o].statusses[0].duration){value++}}
                }
                this.alliedEngines[i][0].cardHealth+=value
                if(this.oppSpyI!=null) {this.opponentBoard[this.oppSpyI].cardHealth += value}
                if(this.oppSpyI2!=null) {this.opponentBoard[this.oppSpyI2].cardHealth += value}
            }
            if(this.alliedEngines[i][0].cardEngineCondition=="Outnumbered"){
                if(this.filledBoardSpace.length<this.filledOpponentBoardSpace.length){
                    pass = true
                } else {pass=false}
            }
            if(this.alliedEngines[i][0].statusses[3].duration){pass=false}
            if(pass){
                setTimeout(()=>{
                   if(this.alliedEngines[i][0].cardEngineTarget=="Self"){
                   if(this.alliedEngines[i][0].cardEngineType=="Damage"){
                    if(this.playerBoard[this.alliedEngines[i][1]].damageBondI){this.playerBoard[this.playerBoard[this.alliedEngines[i]].damageBondI].cardHealth -= this.alliedEngines[i][0].cardEngineValue}
                    else if(this.playerBoard[this.alliedEngines[i][1]].statusses[2].status=="Shield"){this.playerBoard[this.alliedEngines[i][1]].statusses[2]={}}
                    else {
                        if(this.alliedEngines[i][1]!=9){if(this.playerBoard[this.alliedEngines[i][1]+1].cardEffect!="Unkillable"){this.playerBoard[this.alliedEngines[i][1]].cardHealth -= this.alliedEngines[i][0].cardEngineValue}}
                        else{this.playerBoard[this.alliedEngines[i][1]].cardHealth -= this.alliedEngines[i][0].cardEngineValue}
                        if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                        if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}}
         } else if(this.alliedEngines[i][0].cardEngineType=="Boost"){
                    this.playerBoard[this.alliedEngines[i][1]].cardHealth += this.alliedEngines[i][0].cardEngineValue
                    if(this.oppSpyI!=null) {this.opponentBoard[this.oppSpyI].cardHealth += this.alliedEngines[i][0].cardEngineValue}
                    if(this.oppSpyI2!=null) {this.opponentBoard[this.oppSpyI2].cardHealth += this.alliedEngines[i][0].cardEngineValue}}
            } else if(this.alliedEngines[i][0].cardEngineTarget=="Left"){
                if(this.alliedEngines[i][0].cardEngineType=="Boost"){
                    if(this.alliedEngines[i][1]!=0){if(this.playerBoard[this.alliedEngines[i][1]-1].cardName){
                        this.playerBoard[this.alliedEngines[i][1]-1].cardHealth += this.alliedEngines[i][0].cardEngineValue
                        if(this.playerBoard[this.alliedEngines[i][1]-1].cardEngineCondition=="Received Boost"){this.playerBoard[this.alliedEngines[i][1]-1].cardEngineValue++}
                        if(this.oppSpyI!=null && this.playerBoard[this.alliedEngines[i][1]-1].cardName) {this.opponentBoard[this.oppSpyI].cardHealth += this.alliedEngines[i][0].cardEngineValue}
                        if(this.oppSpyI2!=null && this.playerBoard[this.alliedEngines[i][1]-1].cardName) {this.opponentBoard[this.oppSpyI2].cardHealth += this.alliedEngines[i][0].cardEngineValue}
                        }}}
           else if(this.alliedEngines[i][0].cardEngineType=="Damage"){
                    if(this.alliedEngines[i][1]!=0){if(this.playerBoard[this.alliedEngines[i][1]-1].cardName){
                      if(this.playerBoard[this.alliedEngines[i][1]-1].damageBondI){this.playerBoard[this.playerBoard[this.alliedEngines[i]].damageBondI].cardHealth -= this.alliedEngines[i][0].cardEngineValue}
                      else if(this.playerBoard[this.alliedEngines[i][1]-1].statusses[2].status=="Shield"){this.playerBoard[this.alliedEngines[i][1]-1].statusses[2]={}}
                      else {
                          this.playerBoard[this.alliedEngines[i][1]-1].cardHealth -= this.alliedEngines[i][0].cardEngineValue
                          if(this.playerBoard[this.alliedEngines[i][1]-1].cardEngineCondition=="Damage Taken"){this.playerBoard[this.alliedEngines[i][1]-1].cardEngineValue++}
                          if(this.chiefI!=null && this.playerBoard[this.alliedEngines[i][1]-1].cardName){this.playerBoard[this.chiefI].cardEngineValue++}
                          if(this.chiefI2!=null && this.playerBoard[this.alliedEngines[i][1]-1].cardName){this.playerBoard[this.chiefI2].cardEngineValue++}}}}}
            } else if(this.alliedEngines[i][0].cardEngineTarget=="Right"){
                    if(this.alliedEngines[i][0].cardEngineType=="Boost"){
                        if(this.alliedEngines[i][1]!=9){if(this.playerBoard[this.alliedEngines[i][1]+1].cardName){
                            this.playerBoard[this.alliedEngines[i][1]+1].cardHealth += this.alliedEngines[i][0].cardEngineValue
                            if(this.playerBoard[this.alliedEngines[i][1]+1].cardEngineCondition=="Received Boost"){this.playerBoard[this.alliedEngines[i][1]+1].cardEngineValue++}
                            if(this.oppSpyI!=null && this.playerBoard[this.alliedEngines[i][1]+1].cardName) {this.opponentBoard[this.oppSpyI].cardHealth += this.alliedEngines[i][0].cardEngineValue}
                            if(this.oppSpyI2!=null && this.playerBoard[this.alliedEngines[i][1]+1].cardName) {this.opponentBoard[this.oppSpyI2].cardHealth += this.alliedEngines[i][0].cardEngineValue}}}
                } else if(this.alliedEngines[i][0].cardEngineType=="Damage"){
                    if(this.alliedEngines[i][1]!=9){if(this.playerBoard[this.alliedEngines[i][1]+1].cardName){
                      if(this.playerBoard[this.alliedEngines[i][1]+1].damageBondI){
                        this.playerBoard[this.playerBoard[this.alliedEngines[i]].damageBondI].cardHealth -= this.alliedEngines[i][0].cardEngineValue
                    } else if(this.playerBoard[this.alliedEngines[i][1]+1].statusses[2].status=="Shield"){
                      this.playerBoard[this.alliedEngines[i][1]+1].statusses[2]={}
                    } else {
                        if(this.alliedEngines[i][1]<8){if(this.playerBoard[this.alliedEngines[i][1]+2].cardEffect!="Unkillable"){this.playerBoard[this.alliedEngines[i][1]+1].cardHealth -= this.alliedEngines[i][0].cardEngineValue}}
                        else{this.playerBoard[this.alliedEngines[i][1]+1].cardHealth -= this.alliedEngines[i][0].cardEngineValue}
                        if(this.playerBoard[this.alliedEngines[i][1]+1].cardEngineCondition=="Damage Taken"){this.playerBoard[this.alliedEngines[i][1]+1].cardEngineValue++}
                        if(this.chiefI!=null && this.playerBoard[this.alliedEngines[i][1]+1].cardName){this.playerBoard[this.chiefI].cardEngineValue++}
                        if(this.chiefI2!=null && this.playerBoard[this.alliedEngines[i][1]+1].cardName){this.playerBoard[this.chiefI2].cardEngineValue++}}}}}
            } else if(this.alliedEngines[i][0].cardEngineTarget=="Adjacent"){
                if(this.alliedEngines[i][0].cardEngineType=="Boost"){
                    if(this.alliedEngines[i][1]!=0){if(this.playerBoard[this.alliedEngines[i][1]-1].cardName){
                        this.playerBoard[this.alliedEngines[i][1]-1].cardHealth += this.alliedEngines[i][0].cardEngineValue
                        if(this.playerBoard[this.alliedEngines[i][1]-1].cardEngineCondition=="Received Boost"){this.playerBoard[this.alliedEngines[i][1]-1].cardEngineValue++}
                        if(this.oppSpyI!=null && this.playerBoard[this.alliedEngines[i][1]-1].cardName) {this.opponentBoard[this.oppSpyI].cardHealth += this.alliedEngines[i][0].cardEngineValue}
                        if(this.oppSpyI2!=null && this.playerBoard[this.alliedEngines[i][1]-1].cardName) {this.opponentBoard[this.oppSpyI2].cardHealth += this.alliedEngines[i][0].cardEngineValue}
                        }}
                    if(this.alliedEngines[i][1]!=9){if(this.playerBoard[this.alliedEngines[i][1]+1].cardName){
                        this.playerBoard[this.alliedEngines[i][1]+1].cardHealth += this.alliedEngines[i][0].cardEngineValue
                        if(this.playerBoard[this.alliedEngines[i][1]+1].cardEngineCondition=="Received Boost"){this.playerBoard[this.alliedEngines[i][1]+1].cardEngineValue++}
                        if(this.oppSpyI!=null && this.playerBoard[this.alliedEngines[i][1]+1].cardName) {this.opponentBoard[this.oppSpyI].cardHealth += this.alliedEngines[i][0].cardEngineValue}
                        if(this.oppSpyI2!=null && this.playerBoard[this.alliedEngines[i][1]+1].cardName) {this.opponentBoard[this.oppSpyI2].cardHealth += this.alliedEngines[i][0].cardEngineValue}
                        }}
                } else if(this.alliedEngines[i][0].cardEngineType=="Damage"){
                    if(this.alliedEngines[i][1]!=0){if(this.playerBoard[this.alliedEngines[i][1]-1].cardName){
                      if(this.playerBoard[this.alliedEngines[i][1]-1].damageBondI){this.playerBoard[this.playerBoard[this.alliedEngines[i][1]-1].damageBondI].cardHealth -= this.alliedEngines[i][0].cardEngineValue}
                      else if(this.playerBoard[this.alliedEngines[i][1]-1].statusses[2].status=="Shield"){this.playerBoard[this.alliedEngines[i][1]-1].statusses[2]={}}
                      else {
                        this.playerBoard[this.alliedEngines[i][1]-1].cardHealth -= this.alliedEngines[i][0].cardEngineValue
                        if(this.playerBoard[this.alliedEngines[i][1]-1].cardEngineCondition=="Damage Taken"){this.playerBoard[this.alliedEngines[i][1]-1].cardEngineValue++}
                        if(this.chiefI!=null && this.playerBoard[this.alliedEngines[i][1]-1].cardName){this.playerBoard[this.chiefI].cardEngineValue++}
                        if(this.chiefI2!=null && this.playerBoard[this.alliedEngines[i][1]-1].cardName){this.playerBoard[this.chiefI2].cardEngineValue++}
                        if(this.alliedEngines[i][0].cardEngineCondition=="Damaged Allies"){this.alliedEngines[i][0].cardEngineValue2++}}}}
                     if(this.alliedEngines[i][1]!=9){if(this.playerBoard[this.alliedEngines[i][1]+1].cardName){
                      if(this.playerBoard[this.alliedEngines[i][1]+1].damageBondI){this.playerBoard[this.playerBoard[this.alliedEngines[i][1]+1].damageBondI].cardHealth -= this.alliedEngines[i][0].cardEngineValue}
                      else if(this.playerBoard[this.alliedEngines[i][1]+1].statusses[2].status=="Shield"){this.playerBoard[this.alliedEngines[i][1]+1].statusses[2]={}}
                      else {
                        if(this.alliedEngines[i][1]<8){if(this.playerBoard[this.alliedEngines[i][1]+2].cardEffect!="Unkillable"){this.playerBoard[this.alliedEngines[i][1]+1].cardHealth -= this.alliedEngines[i][0].cardEngineValue}}
                        else{this.playerBoard[this.alliedEngines[i][1]+1].cardHealth -= this.alliedEngines[i][0].cardEngineValue}
                        if(this.playerBoard[this.alliedEngines[i][1]+1].cardEngineCondition=="Damage Taken"){this.playerBoard[this.alliedEngines[i][1]+1].cardEngineValue++}
                        if(this.chiefI!=null && this.playerBoard[this.alliedEngines[i][1]+1].cardName){this.playerBoard[this.chiefI].cardEngineValue++}
                        if(this.chiefI2!=null && this.playerBoard[this.alliedEngines[i][1]+1].cardName){this.playerBoard[this.chiefI2].cardEngineValue++}
                        if(this.alliedEngines[i][0].cardEngineCondition=="Damaged Allies"){this.alliedEngines[i][0].cardEngineValue2++}}}
                }}
            } else if(this.alliedEngines[i][0].cardEngineTarget=="Random"){
                if(this.alliedEngines[i][0].cardTargetUnitType=="Ally"){
                    if(this.alliedEngines[i][0].cardEngineType=="Boost"){
                        if(this.filledBoardSpace.length>0){
                            let unit = this.playerBoard[this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]]
                            unit.cardHealth += this.alliedEngines[i][0].cardEngineValue
                            if(unit.cardEngineCondition=="Received Boost"){unit.cardEngineValue++}
                            if(this.oppSpyI!=null) {this.opponentBoard[this.oppSpyI].cardHealth += this.alliedEngines[i][0].cardEngineValue}
                            if(this.oppSpyI2!=null) {this.opponentBoard[this.oppSpyI2].cardHealth += this.alliedEngines[i][0].cardEngineValue}
                            }
             } else if(this.alliedEngines[i][0].cardEngineType=="Damage"){
                        if(this.filledBoardSpace.length>0){
                          let unitI = this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]
                            if(this.playerBoard[unitI].damageBondI) {this.playerBoard[this.playerBoard[unitI].damageBondI] -= this.alliedEngines[i][0].cardEngineValue}
                            else if(this.playerBoard[unitI].statusses[2].status=="Shield"){this.playerBoard[unitI].statusses[2]={}}
                              else {
                              if(unitI!=9){if(this.playerBoard[unitI+1].cardEffect!="Unkillable"){this.playerBoard[unitI].cardHealth -= this.alliedEngines[i][0].cardEngineValue}}
                              else{this.playerBoard[unitI].cardHealth -= this.alliedEngines[i][0].cardEngineValue}
                              if(this.playerBoard[unitI].cardEngineCondition=="Damage Taken"){this.playerBoard[unitI].cardEngineValue++}
                              if(this.chiefI!=null && this.playerBoard[unitI].cardName){this.playerBoard[this.chiefI].cardEngineValue++}
                              if(this.chiefI2!=null && this.playerBoard[unitI].cardName){this.playerBoard[this.chiefI2].cardEngineValue++}}}
                    }
            }   else if(this.alliedEngines[i][0].cardTargetUnitType=="Enemy"){
                    if(this.alliedEngines[i][0].cardEngineType=="Boost"){
                        if(this.filledOpponentBoardSpace.length>0){
                            let unit = this.opponentBoard[this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]]
                            unit.cardHealth += this.alliedEngines[i][0].cardEngineValue
                            if(unit.cardEngineCondition=="Received Boost"){unit.cardEngineValue++}
                            if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.alliedEngines[i][0].cardEngineValue}
                            if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.alliedEngines[i][0].cardEngineValue}
                        }
             } else if(this.alliedEngines[i][0].cardEngineType=="Damage"){
                        if(this.filledOpponentBoardSpace.length>0){
                            let unitI = this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]
                            if(this.opponentBoard[unitI].damageBondI) {this.opponentBoard[this.opponentBoard[unitI].damageBondI] -= this.alliedEngines[i][0].cardEngineValue}
                            else if(this.opponentBoard[unitI].statusses[2].status=="Shield"){this.opponentBoard[unitI].statusses[2]={}}
                              else {
                              if(unitI!=9){if(this.opponentBoard[unitI+1].cardEffect!="Unkillable"){this.opponentBoard[unitI].cardHealth -= this.alliedEngines[i][0].cardEngineValue}}
                              else{this.opponentBoard[unitI].cardHealth -= this.alliedEngines[i][0].cardEngineValue}
                              if(this.opponentBoard[unitI].cardEngineCondition=="Damage Taken"){this.opponentBoard[unitI].cardEngineValue++}
                              if(this.oppChiefI!=null && this.opponentBoard[unitI].cardName){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                              if(this.oppChiefI2!=null && this.opponentBoard[unitI].cardName){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}
                    }
                }
                if(this.alliedEngines[i][0].cardEngineCondition=="Damage Taken" || this.alliedEngines[i][0].cardEngineCondition=="Received Boost" || this.alliedEngines[i][0].cardEngineCondition=="Damaged Allies"){this.alliedEngines[i][0].cardEngineValue=0}}
            }      if(this.alliedEngines[i][0].cardEngineType=="Removal"){
                if(this.alliedEngines[i][0].cardEngineTarget=="Lowest Health Enemy"){
                    let lowestHealth = null
                    let lowestHealthUnitI = null
                    for(let o = 0; o < this.opponentBoard.length; o++){
                        for(let u = 0; u < this.opponentBoard.length; u++){
                            if(this.opponentBoard[o].cardHealth > this.opponentBoard[u].cardHealth){break}
                            if(u == this.opponentBoard.length-1){
                                if(lowestHealth!=null){if(this.opponentBoard[o].cardHealth < lowestHealth){lowestHealth=this.opponentBoard[o].cardHealth; lowestHealthUnitI = o}
                              } else{lowestHealth=this.opponentBoard[o].cardHealth; lowestHealthUnitI = o}}}}
                    this.opponentBoard[lowestHealthUnitI].cardHealth=0
                }
            }
                   if(this.alliedEngines[i][0].cardEngineTarget2=="Self"){
                if(this.alliedEngines[i][0].cardEngineType2=="Damage"){
                    if(this.playerBoard[this.alliedEngines[i][1]].damageBondI){this.playerBoard[this.playerBoard[this.alliedEngines[i]].damageBondI].cardHealth -= this.alliedEngines[i][0].cardEngineValue2}
                    else if(this.playerBoard[this.alliedEngines[i][1]].statusses[2].status=="Shield"){this.playerBoard[this.alliedEngines[i][1]].statusses[2]={}}
                    else {
                        if(this.alliedEngines[i][1]!=9){if(this.playerBoard[this.alliedEngines[i][1]+1].cardEffect!="Unkillable"){this.playerBoard[this.alliedEngines[i][1]].cardHealth -= this.alliedEngines[i][0].cardEngineValue2}}
                        else{this.playerBoard[this.alliedEngines[i][1]].cardHealth -= this.alliedEngines[i][0].cardEngineValue2}
                        if(this.chiefI!=null){this.playerBoard[this.chiefI].cardEngineValue++}
                        if(this.chiefI2!=null){this.playerBoard[this.chiefI2].cardEngineValue++}}
         } else if(this.alliedEngines[i][0].cardEngineType2=="Boost"){
                    this.playerBoard[this.alliedEngines[i][1]].cardHealth += this.alliedEngines[i][0].cardEngineValue2
                    if(this.oppSpyI!=null) {this.opponentBoard[this.oppSpyI].cardHealth += this.alliedEngines[i][0].cardEngineValue2}
                    if(this.oppSpyI2!=null) {this.opponentBoard[this.oppSpyI2].cardHealth += this.alliedEngines[i][0].cardEngineValue2}}
            } else if(this.alliedEngines[i][0].cardEngineTarget2=="Left"){
                if(this.alliedEngines[i][0].cardEngineType2=="Boost"){
                    if(this.alliedEngines[i][1]!=0){if(this.playerBoard[this.alliedEngines[i][1]-1].cardName){
                        this.playerBoard[this.alliedEngines[i][1]-1].cardHealth += this.alliedEngines[i][0].cardEngineValue2
                        if(this.playerBoard[this.alliedEngines[i][1]-1].cardEngineCondition=="Received Boost"){this.playerBoard[this.alliedEngines[i][1]-1].cardEngineValue++}
                        if(this.oppSpyI!=null && this.playerBoard[this.alliedEngines[i][1]-1].cardName) {this.opponentBoard[this.oppSpyI].cardHealth += this.alliedEngines[i][0].cardEngineValue2}
                        if(this.oppSpyI2!=null && this.playerBoard[this.alliedEngines[i][1]-1].cardName) {this.opponentBoard[this.oppSpyI2].cardHealth += this.alliedEngines[i][0].cardEngineValue2}
                        }}}
           else if(this.alliedEngines[i][0].cardEngineType2=="Damage"){
                    if(this.alliedEngines[i][1]!=0){if(this.playerBoard[this.alliedEngines[i][1]-1].cardName){
                      if(this.playerBoard[this.alliedEngines[i][1]-1].damageBondI){this.playerBoard[this.playerBoard[this.alliedEngines[i]].damageBondI].cardHealth -= this.alliedEngines[i][0].cardEngineValue2}
                      else if(this.playerBoard[this.alliedEngines[i][1]-1].statusses[2].status=="Shield"){this.playerBoard[this.alliedEngines[i][1]-1].statusses[2]={}}
                      else {
                          this.playerBoard[this.alliedEngines[i][1]-1].cardHealth -= this.alliedEngines[i][0].cardEngineValue2
                          if(this.playerBoard[this.alliedEngines[i][1]-1].cardEngineCondition=="Damage Taken"){this.playerBoard[this.alliedEngines[i][1]-1].cardEngineValue++}
                          if(this.chiefI!=null && this.playerBoard[this.alliedEngines[i][1]-1].cardName){this.playerBoard[this.chiefI].cardEngineValue++}
                          if(this.chiefI2!=null && this.playerBoard[this.alliedEngines[i][1]-1].cardName){this.playerBoard[this.chiefI2].cardEngineValue++}}}}}
            } else if(this.alliedEngines[i][0].cardEngineTarget2=="Right"){
                    if(this.alliedEngines[i][0].cardEngineType2=="Boost"){
                        if(this.alliedEngines[i][1]!=9){if(this.playerBoard[this.alliedEngines[i][1]+1].cardName){
                            this.playerBoard[this.alliedEngines[i][1]+1].cardHealth += this.alliedEngines[i][0].cardEngineValue2
                            if(this.playerBoard[this.alliedEngines[i][1]+1].cardEngineCondition=="Received Boost"){this.playerBoard[this.alliedEngines[i][1]+1].cardEngineValue++}
                            if(this.oppSpyI!=null && this.playerBoard[this.alliedEngines[i][1]+1].cardName) {this.opponentBoard[this.oppSpyI].cardHealth += this.alliedEngines[i][0].cardEngineValue2}
                            if(this.oppSpyI2!=null && this.playerBoard[this.alliedEngines[i][1]+1].cardName) {this.opponentBoard[this.oppSpyI2].cardHealth += this.alliedEngines[i][0].cardEngineValue2}}}
                } else if(this.alliedEngines[i][0].cardEngineType2=="Damage"){
                    if(this.alliedEngines[i][1]!=9){if(this.playerBoard[this.alliedEngines[i][1]+1].cardName){
                      if(this.playerBoard[this.alliedEngines[i][1]+1].damageBondI){
                        this.playerBoard[this.playerBoard[this.alliedEngines[i]].damageBondI].cardHealth -= this.alliedEngines[i][0].cardEngineValue2
                    } else if(this.playerBoard[this.alliedEngines[i][1]+1].statusses[2].status=="Shield"){
                      this.playerBoard[this.alliedEngines[i][1]+1].statusses[2]={}
                    } else {
                        if(this.alliedEngines[i][1]<8){if(this.playerBoard[this.alliedEngines[i][1]+2].cardEffect!="Unkillable"){this.playerBoard[this.alliedEngines[i][1]+1].cardHealth -= this.alliedEngines[i][0].cardEngineValue2}}
                        else{this.playerBoard[this.alliedEngines[i][1]+1].cardHealth -= this.alliedEngines[i][0].cardEngineValue2}
                        if(this.playerBoard[this.alliedEngines[i][1]+1].cardEngineCondition=="Damage Taken"){this.playerBoard[this.alliedEngines[i][1]+1].cardEngineValue++}
                        if(this.chiefI!=null && this.playerBoard[this.alliedEngines[i][1]+1].cardName){this.playerBoard[this.chiefI].cardEngineValue++}
                        if(this.chiefI2!=null && this.playerBoard[this.alliedEngines[i][1]+1].cardName){this.playerBoard[this.chiefI2].cardEngineValue++}}}}}
            } else if(this.alliedEngines[i][0].cardEngineTarget2=="Adjacent"){
                if(this.alliedEngines[i][0].cardEngineType2=="Boost"){
                    if(this.alliedEngines[i][1]!=0){if(this.playerBoard[this.alliedEngines[i][1]-1].cardName){
                        this.playerBoard[this.alliedEngines[i][1]-1].cardHealth += this.alliedEngines[i][0].cardEngineValue2
                        if(this.playerBoard[this.alliedEngines[i][1]-1].cardEngineCondition=="Received Boost"){this.playerBoard[this.alliedEngines[i][1]-1].cardEngineValue++}
                        if(this.oppSpyI!=null && this.playerBoard[this.alliedEngines[i][1]-1].cardName) {this.opponentBoard[this.oppSpyI].cardHealth += this.alliedEngines[i][0].cardEngineValue2}
                        if(this.oppSpyI2!=null && this.playerBoard[this.alliedEngines[i][1]-1].cardName) {this.opponentBoard[this.oppSpyI2].cardHealth += this.alliedEngines[i][0].cardEngineValue2}
                        }}
                    if(this.alliedEngines[i][1]!=9){if(this.playerBoard[this.alliedEngines[i][1]+1].cardName){
                        this.playerBoard[this.alliedEngines[i][1]+1].cardHealth += this.alliedEngines[i][0].cardEngineValue2
                        if(this.playerBoard[this.alliedEngines[i][1]+1].cardEngineCondition=="Received Boost"){this.playerBoard[this.alliedEngines[i][1]+1].cardEngineValue++}
                        if(this.oppSpyI!=null && this.playerBoard[this.alliedEngines[i][1]+1].cardName) {this.opponentBoard[this.oppSpyI].cardHealth += this.alliedEngines[i][0].cardEngineValue2}
                        if(this.oppSpyI2!=null && this.playerBoard[this.alliedEngines[i][1]+1].cardName) {this.opponentBoard[this.oppSpyI2].cardHealth += this.alliedEngines[i][0].cardEngineValue2}
                        }}
                } else if(this.alliedEngines[i][0].cardEngineType2=="Damage"){
                    if(this.alliedEngines[i][1]!=0){if(this.playerBoard[this.alliedEngines[i][1]-1].cardName){
                      if(this.playerBoard[this.alliedEngines[i][1]-1].damageBondI){this.playerBoard[this.playerBoard[this.alliedEngines[i][1]-1].damageBondI].cardHealth -= this.alliedEngines[i][0].cardEngineValue2}
                      else if(this.playerBoard[this.alliedEngines[i][1]-1].statusses[2].status=="Shield"){this.playerBoard[this.alliedEngines[i][1]-1].statusses[2]={}}
                      else {
                        this.playerBoard[this.alliedEngines[i][1]-1].cardHealth -= this.alliedEngines[i][0].cardEngineValue2
                        if(this.playerBoard[this.alliedEngines[i][1]-1].cardEngineCondition=="Damage Taken"){this.playerBoard[this.alliedEngines[i][1]-1].cardEngineValue++}
                    }   if(this.chiefI!=null && this.playerBoard[this.alliedEngines[i][1]-1].cardName){this.playerBoard[this.chiefI].cardEngineValue++}
                        if(this.chiefI2!=null && this.playerBoard[this.alliedEngines[i][1]-1].cardName){this.playerBoard[this.chiefI2].cardEngineValue++}
                        this.alliedEngines[i][0].cardEngineValue2++
                }}   if(this.alliedEngines[i][1]!=9){if(this.playerBoard[this.alliedEngines[i][1]+1].cardName){
                      if(this.playerBoard[this.alliedEngines[i][1]+1].damageBondI){this.playerBoard[this.playerBoard[this.alliedEngines[i][1]+1].damageBondI].cardHealth -= this.alliedEngines[i][0].cardEngineValue2}
                      else if(this.playerBoard[this.alliedEngines[i][1]+1].statusses[2].status=="Shield"){this.playerBoard[this.alliedEngines[i][1]+1].statusses[2]={}}
                      else {
                        if(this.alliedEngines[i][1]<8){if(this.playerBoard[this.alliedEngines[i][1]+2].cardEffect!="Unkillable"){this.playerBoard[this.alliedEngines[i][1]+1].cardHealth -= this.alliedEngines[i][0].cardEngineValue2}}
                        else{this.playerBoard[this.alliedEngines[i][1]+1].cardHealth -= this.alliedEngines[i][0].cardEngineValue2}
                        if(this.playerBoard[this.alliedEngines[i][1]+1].cardEngineCondition=="Damage Taken"){this.playerBoard[this.alliedEngines[i][1]+1].cardEngineValue++}
                    }   if(this.chiefI!=null && this.playerBoard[this.alliedEngines[i][1]+1].cardName){this.playerBoard[this.chiefI].cardEngineValue++}
                        if(this.chiefI2!=null && this.playerBoard[this.alliedEngines[i][1]+1].cardName){this.playerBoard[this.chiefI2].cardEngineValue++}
                        this.alliedEngines[i][0].cardEngineValue2++
                }}}
            } else if(this.alliedEngines[i][0].cardEngineTarget2=="Random"){
                if(this.alliedEngines[i][0].cardTargetUnitType2=="Ally"){
                    if(this.alliedEngines[i][0].cardEngineType2=="Boost"){
                        if(this.filledBoardSpace.length>0){
                            let unit = this.playerBoard[this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]]
                            unit.cardHealth += this.alliedEngines[i][0].cardEngineValue2
                            if(unit.cardEngineCondition=="Received Boost"){unit.cardEngineValue++}
                            if(this.oppSpyI!=null) {this.opponentBoard[this.oppSpyI].cardHealth += this.alliedEngines[i][0].cardEngineValue2}
                            if(this.oppSpyI2!=null) {this.opponentBoard[this.oppSpyI2].cardHealth += this.alliedEngines[i][0].cardEngineValue2}
                            }
             } else if(this.alliedEngines[i][0].cardEngineType2=="Damage"){
                        if(this.filledBoardSpace.length>0){
                          let unitI = this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]
                            if(this.playerBoard[unitI].damageBondI) {this.playerBoard[this.playerBoard[unitI].damageBondI] -= this.alliedEngines[i][0].cardEngineValue2}
                            else if(this.playerBoard[unitI].statusses[2].status=="Shield"){this.playerBoard[unitI].statusses[2]={}}
                              else {
                                if(unitI!=9){if(this.playerBoard[unitI+1].cardEffect!="Unkillable"){this.playerBoard[unitI].cardHealth -= this.alliedEngines[i][0].cardEngineValue2}}
                                else{this.playerBoard[unitI].cardHealth -= this.alliedEngines[i][0].cardEngineValue2}
                                if(this.playerBoard[unitI].cardEngineCondition=="Damage Taken"){this.playerBoard[unitI].cardEngineValue++}
                                if(this.chiefI!=null && this.playerBoard[unitI].cardName){this.playerBoard[this.chiefI].cardEngineValue++}
                                if(this.chiefI2!=null && this.playerBoard[unitI].cardName){this.playerBoard[this.chiefI2].cardEngineValue++}}}
                    }
            }   else if(this.alliedEngines[i][0].cardTargetUnitType2=="Enemy"){
                    if(this.alliedEngines[i][0].cardEngineType2=="Boost"){
                        if(this.filledOpponentBoardSpace.length>0){
                            let unit = this.opponentBoard[this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]]
                            unit.cardHealth += this.alliedEngines[i][0].cardEngineValue2
                            if(unit.cardEngineCondition=="Received Boost"){unit.cardEngineValue++}
                            if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.alliedEngines[i][0].cardEngineValue2}
                            if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.alliedEngines[i][0].cardEngineValue2}
                        }
             } else if(this.alliedEngines[i][0].cardEngineType2=="Damage"){
                        if(this.filledOpponentBoardSpace.length>0){
                            let unitI = this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]
                            if(this.opponentBoard[unitI].damageBondI) {this.opponentBoard[this.opponentBoard[unitI].damageBondI] -= this.alliedEngines[i][0].cardEngineValue2}
                            else if(this.opponentBoard[unitI].statusses[2].status=="Shield"){this.opponentBoard[unitI].statusses[2]={}}
                              else {
                                if(unitI!=9){if(this.opponentBoard[unitI+1].cardEffect!="Unkillable"){this.opponentBoard[unitI].cardHealth -= this.alliedEngines[i][0].cardEngineValue2}}
                                else{this.opponentBoard[unitI].cardHealth -= this.alliedEngines[i][0].cardEngineValue2}
                                if(this.opponentBoard[unitI].cardEngineCondition=="Damage Taken"){this.opponentBoard[unitI].cardEngineValue++}
                                if(this.oppChiefI!=null && this.opponentBoard[unitI].cardName){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                                if(this.oppChiefI2!=null && this.opponentBoard[unitI].cardName){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}
                    }
                }
                if(this.alliedEngines[i][0].cardEngineCondition2=="Damage Taken" || this.alliedEngines[i][0].cardEngineCondition2=="Received Boost" || this.alliedEngines[i][0].cardEngineCondition2=="Allied Unit Damaged"){this.alliedEngines[i][0].cardEngineValue2=0}}
            }
            }, 200)
          }}, 100)}
      },
      processEnemyEngines(){
         for(let i=0; i < this.opponentEngines.length; i++){
            setTimeout(() => { 
            let pass = true
            if(this.opponentEngines[i][0].cardEngineCondition=="Number Of Enemy Units With Bleeding"){
                let value = 0
                for(let o = 0; o < 10; o++){
                    if(this.playerBoard[o].cardHealth){if(this.playerBoard[o].statusses[0].status=="Bleeding"){value++}}
                }
                this.opponentEngines[i][0].cardHealth+=value
                if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += value}
                if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += value}
            }
            if(this.opponentEngines[i][0].cardEngineCondition=="Enemy Has More Units"){
                let playerLength = 0
                let opponentLength = 0
                for(let o = 0; o < 10; o++){if(this.opponentBoard[o].cardName){opponentLength++}}
                for(let o = 0; o < 10; o++){if(this.playerBoard[o].cardName){playerLength++}}
                if(playerLength <= opponentLength){
                    pass=false
                }
            }
            if(this.opponentEngines[i][0].cardEngineCondition=="Alone"){
                if(this.filledOpponentBoardSpace.length==1){
                    pass = true
                } else {pass=false}
            }
            if(this.opponentEngines[i][0].statusses[3].duration){pass=false}
            if(pass){
                   setTimeout(()=>{
                   if(this.opponentEngines[i][0].cardEngineTarget=="Self"){
                if(this.opponentEngines[i][0].cardEngineType=="Damage"){
                    if(this.opponentBoard[this.opponentEngines[i][1]].damageBondI){this.opponentBoard[this.opponentBoard[this.opponentEngines[i]].damageBondI].cardHealth -= this.opponentEngines[i][0].cardEngineValue}
                    else if(this.opponentBoard[this.opponentEngines[i][1]].statusses[2].status=="Shield"){this.opponentBoard[this.opponentEngines[i][1]].statusses[2]={}}
                    else {
                        if(this.opponentEngines[i][1]!=9){if(this.opponentBoard[this.opponentEngines[i][1]+1].cardEffect!="Unkillable"){this.opponentBoard[this.opponentEngines[i][1]].cardHealth -= this.opponentEngines[i][0].cardEngineValue}}
                        else{this.opponentBoard[this.opponentEngines[i][1]].cardHealth -= this.opponentEngines[i][0].cardEngineValue}
                        if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                        if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}
         } else if(this.opponentEngines[i][0].cardEngineType=="Boost"){
                    this.opponentBoard[this.opponentEngines[i][1]].cardHealth += this.opponentEngines[i][0].cardEngineValue
                    if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentEngines[i][0].cardEngineValue}
                    if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentEngines[i][0].cardEngineValue}}
            } else if(this.opponentEngines[i][0].cardEngineTarget=="Left"){
                if(this.opponentEngines[i][0].cardEngineType=="Boost"){
                    if(this.opponentEngines[i][1]!=0){if(this.opponentBoard[this.opponentEngines[i][1]-1].cardName){
                        this.opponentBoard[this.opponentEngines[i][1]-1].cardHealth += this.opponentEngines[i][0].cardEngineValue
                        if(this.opponentBoard[this.opponentEngines[i][1]-1].cardEngineCondition=="Received Boost"){this.opponentBoard[this.opponentEngines[i][1]-1].cardEngineValue++}
                        if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentEngines[i][0].cardEngineValue}
                        if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentEngines[i][0].cardEngineValue}
                        }}}
           else if(this.opponentEngines[i][0].cardEngineType=="Damage"){
                    if(this.opponentEngines[i][1]!=0){if(this.opponentBoard[this.opponentEngines[i][1]-1].cardName){
                      if(this.opponentBoard[this.opponentEngines[i][1]-1].damageBondI){this.opponentBoard[this.opponentBoard[this.opponentEngines[i]].damageBondI].cardHealth -= this.opponentEngines[i][0].cardEngineValue}
                      else if(this.opponentBoard[this.opponentEngines[i][1]-1].statusses[2].status=="Shield"){this.opponentBoard[this.opponentEngines[i][1]-1].statusses[2]={}}
                      else {
                          this.opponentBoard[this.opponentEngines[i][1]-1].cardHealth -= this.opponentEngines[i][0].cardEngineValue
                          if(this.opponentBoard[this.opponentEngines[i][1]-1].cardEngineCondition=="Damage Taken"){this.opponentBoard[this.opponentEngines[i][1]-1].cardEngineValue++}
                          if(this.oppChiefI!=null && this.opponentBoard[this.opponentEngines[i][1]-1].cardName){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                          if(this.oppChiefI2!=null && this.opponentBoard[this.opponentEngines[i][1]-1].cardName){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}}}}
            } else if(this.opponentEngines[i][0].cardEngineTarget=="Right"){
                    if(this.opponentEngines[i][0].cardEngineType=="Boost"){
                        if(this.opponentEngines[i][1]!=9){if(this.opponentBoard[this.opponentEngines[i][1]+1].cardName){
                            this.opponentBoard[this.opponentEngines[i][1]+1].cardHealth += this.opponentEngines[i][0].cardEngineValue
                            if(this.opponentBoard[this.opponentEngines[i][1]+1].cardEngineCondition=="Received Boost"){this.opponentBoard[this.opponentEngines[i][1]+1].cardEngineValue++}
                            if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentEngines[i][0].cardEngineValue}
                            if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentEngines[i][0].cardEngineValue}}}
                } else if(this.opponentEngines[i][0].cardEngineType=="Damage"){
                    if(this.opponentEngines[i][1]!=9){if(this.opponentBoard[this.opponentEngines[i][1]+1].cardName){
                      if(this.opponentBoard[this.opponentEngines[i][1]+1].damageBondI){
                        this.opponentBoard[this.opponentBoard[this.opponentEngines[i]].damageBondI].cardHealth -= this.opponentEngines[i][0].cardEngineValue
                    } else if(this.opponentBoard[this.opponentEngines[i][1]+1].statusses[2].status=="Shield"){
                      this.opponentBoard[this.opponentEngines[i][1]+1].statusses[2]={}
                    } else {
                        if(this.opponentEngines[i][1]<8){if(this.opponentBoard[this.opponentEngines[i][1]+2].cardEffect!="Unkillable"){this.opponentBoard[this.opponentEngines[i][1]+1].cardHealth -= this.opponentEngines[i][0].cardEngineValue}}
                        else{this.opponentBoard[this.opponentEngines[i][1]+1].cardHealth -= this.opponentEngines[i][0].cardEngineValue}
                        if(this.opponentBoard[this.opponentEngines[i][1]+1].cardEngineCondition=="Damage Taken"){this.opponentBoard[this.opponentEngines[i][1]+1].cardEngineValue++}
                        if(this.oppChiefI!=null && this.opponentBoard[this.opponentEngines[i][1]+1].cardName){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                        if(this.oppChiefI2!=null && this.opponentBoard[this.opponentEngines[i][1]+1].cardName){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}}}}
            } else if(this.opponentEngines[i][0].cardEngineTarget=="Adjacent"){
                if(this.opponentEngines[i][0].cardEngineType=="Boost"){
                    if(this.opponentEngines[i][1]!=0){if(this.opponentBoard[this.opponentEngines[i][1]-1].cardName){
                        this.opponentBoard[this.opponentEngines[i][1]-1].cardHealth += this.opponentEngines[i][0].cardEngineValue
                        if(this.opponentBoard[this.opponentEngines[i][1]-1].cardEngineCondition=="Received Boost"){this.opponentBoard[this.opponentEngines[i][1]-1].cardEngineValue++}
                        if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentEngines[i][0].cardEngineValue}
                        if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentEngines[i][0].cardEngineValue}
                        }}
                    if(this.opponentEngines[i][1]!=9){if(this.opponentBoard[this.opponentEngines[i][1]+1].cardName){
                        this.opponentBoard[this.opponentEngines[i][1]+1].cardHealth += this.opponentEngines[i][0].cardEngineValue
                        if(this.opponentBoard[this.opponentEngines[i][1]+1].cardEngineCondition=="Received Boost"){this.opponentBoard[this.opponentEngines[i][1]+1].cardEngineValue++}
                        if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentEngines[i][0].cardEngineValue}
                        if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentEngines[i][0].cardEngineValue}
                        }}
                } else if(this.opponentEngines[i][0].cardEngineType=="Damage"){
                    if(this.opponentEngines[i][1]!=0){if(this.opponentBoard[this.opponentEngines[i][1]-1].cardName){
                      if(this.opponentBoard[this.opponentEngines[i][1]-1].damageBondI){this.opponentBoard[this.opponentBoard[this.opponentEngines[i][1]-1].damageBondI].cardHealth -= this.opponentEngines[i][0].cardEngineValue}
                      else if(this.opponentBoard[this.opponentEngines[i][1]-1].statusses[2].status=="Shield"){this.opponentBoard[this.opponentEngines[i][1]-1].statusses[2]={}}
                      else {
                        this.opponentBoard[this.opponentEngines[i][1]-1].cardHealth -= this.opponentEngines[i][0].cardEngineValue
                        if(this.opponentBoard[this.opponentEngines[i][1]-1].cardEngineCondition=="Damage Taken"){this.opponentBoard[this.opponentEngines[i][1]-1].cardEngineValue++}
                        if(this.oppChiefI!=null && this.opponentBoard[this.opponentEngines[i][1]-1].cardName){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                        if(this.oppChiefI2!=null && this.opponentBoard[this.opponentEngines[i][1]-1].cardName){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}}
                        if(this.opponentEngines[i][0].cardEngineCondition=="Damaged Allies"){this.opponentEngines[i][0].cardEngineValue2++}
                }   if(this.opponentEngines[i][1]!=0){if(this.opponentBoard[this.opponentEngines[i][1]+1].cardName){
                      if(this.opponentBoard[this.opponentEngines[i][1]+1].damageBondI){this.opponentBoard[this.opponentBoard[this.opponentEngines[i][1]+1].damageBondI].cardHealth -= this.opponentEngines[i][0].cardEngineValue}
                      else if(this.opponentBoard[this.opponentEngines[i][1]+1].statusses[2].status=="Shield"){this.opponentBoard[this.opponentEngines[i][1]+1].statusses[2]={}}
                      else {
                        if(this.opponentEngines[i][1]<8){if(this.opponentBoard[this.opponentEngines[i][1]+2].cardEffect!="Unkillable"){this.opponentBoard[this.opponentEngines[i][1]+1].cardHealth -= this.opponentEngines[i][0].cardEngineValue}}
                        else{this.opponentBoard[this.opponentEngines[i][1]+1].cardHealth -= this.opponentEngines[i][0].cardEngineValue}
                        if(this.opponentBoard[this.opponentEngines[i][1]+1].cardEngineCondition=="Damage Taken"){this.opponentBoard[this.opponentEngines[i][1]+1].cardEngineValue++}
                        if(this.oppChiefI!=null && this.opponentBoard[this.opponentEngines[i][1]+1].cardName){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                        if(this.oppChiefI2!=null && this.opponentBoard[this.opponentEngines[i][1]+1].cardName){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}
                        if(this.opponentEngines[i][0].cardEngineCondition=="Damaged Allies"){this.opponentEngines[i][0].cardEngineValue2++}
                }}}
            } else if(this.opponentEngines[i][0].cardEngineTarget=="Random"){
                if(this.opponentEngines[i][0].cardTargetUnitType=="Ally"){
                    if(this.opponentEngines[i][0].cardEngineType=="Boost"){
                        if(this.filledOpponentBoardSpace.length>0){
                            let unit = this.opponentBoard[this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]]
                            unit.cardHealth += this.opponentEngines[i][0].cardEngineValue
                            if(unit.cardEngineCondition=="Received Boost"){unit.cardEngineValue++}
                            if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentEngines[i][0].cardEngineValue}
                            if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentEngines[i][0].cardEngineValue}
                            }
             } else if(this.opponentEngines[i][0].cardEngineType=="Damage"){
                        if(this.filledOpponentBoardSpace.length>0){
                          let unitI = this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]
                            if(this.opponentBoard[unitI].damageBondI) {this.opponentBoard[this.opponentBoard[unitI].damageBondI] -= this.opponentEngines[i][0].cardEngineValue}
                            else if(this.opponentBoard[unitI].statusses[2].status=="Shield"){this.opponentBoard[unitI].statusses[2]={}}
                              else {
                              if(unitI!=9){if(this.opponentBoard[unitI+1].cardEffect!="Unkillable"){this.opponentBoard[unitI].cardHealth -= this.opponentEngines[i][0].cardEngineValue}}
                              else{this.opponentBoard[unitI].cardHealth -= this.opponentEngines[i][0].cardEngineValue}
                              if(this.opponentBoard[unitI].cardEngineCondition=="Damage Taken"){this.opponentBoard[unitI].cardEngineValue++}
                            }
                              if(this.oppChiefI!=null && this.opponentBoard[unitI].cardName){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                              if(this.oppChiefI2!=null && this.opponentBoard[unitI].cardName){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}
                    }
            }   else if(this.opponentEngines[i][0].cardTargetUnitType=="Enemy"){
                    if(this.opponentEngines[i][0].cardEngineType=="Boost"){
                        if(this.filledBoardSpace.length>0){
                            let unit = this.playerBoard[this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]]
                            unit.cardHealth += this.opponentEngines[i][0].cardEngineValue
                            if(unit.cardEngineCondition=="Received Boost"){unit.cardEngineValue++}
                            if(this.oppSpyI!=null) {this.opponentBoard[this.oppSpyI].cardHealth += this.opponentEngines[i][0].cardEngineValue}
                            if(this.oppSpyI2!=null) {this.opponentBoard[this.oppSpyI2].cardHealth += this.opponentEngines[i][0].cardEngineValue}
                        }
             } else if(this.opponentEngines[i][0].cardEngineType=="Damage"){
                        if(this.filledBoardSpace.length>0){
                            let unitI = this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]
                            if(this.playerBoard[unitI].damageBondI) {this.playerBoard[this.playerBoard[unitI].damageBondI] -= this.opponentEngines[i][0].cardEngineValue}
                            else if(this.playerBoard[unitI].statusses[2].status=="Shield"){this.playerBoard[unitI].statusses[2]={}}
                              else {
                              if(unitI!=9){if(this.playerBoard[unitI+1].cardEffect!="Unkillable"){this.playerBoard[unitI].cardHealth -= this.opponentEngines[i][0].cardEngineValue}}
                              else{this.playerBoard[unitI].cardHealth -= this.opponentEngines[i][0].cardEngineValue}
                              if(this.playerBoard[unitI].cardEngineCondition=="Damage Taken"){this.playerBoard[unitI].cardEngineValue++}
                              if(this.chiefI!=null && this.playerBoard[unitI].cardName){this.playerBoard[this.chiefI].cardEngineValue++}
                              if(this.chiefI2!=null && this.playerBoard[unitI].cardName){this.playerBoard[this.chiefI2].cardEngineValue++}}
                    }
                }
                if(this.opponentEngines[i][0].cardEngineCondition=="Damage Taken" || this.opponentEngines[i][0].cardEngineCondition=="Received Boost" || this.opponentEngines[i][0].cardEngineCondition=="Allied Unit Damaged"){this.opponentEngines[i][0].cardEngineValue=0}}
            }      if(this.opponentEngines[i][0].cardEngineType=="Removal"){
                if(this.opponentEngines[i][0].cardEngineTarget=="Lowest Health Enemy"){
                    let lowestHealth = null
                    let lowestHealthUnitI = null
                    for(let o = 0; o < this.playerBoard.length; o++){
                        for(let u = 0; u < this.playerBoard.length; u++){
                            if(this.playerBoard[o].cardHealth > this.playerBoard[u].cardHealth){break}
                            if(u == this.playerBoard.length-1){
                                if(lowestHealth!=null){if(this.playerBoard[o].cardHealth < lowestHealth){lowestHealth=this.playerBoard[o].cardHealth; lowestHealthUnitI = o}
                              } else{lowestHealth=this.playerBoard[o].cardHealth; lowestHealthUnitI = o}}}}
                    this.playerBoard[lowestHealthUnitI].cardHealth=0
                }
            }
                   if(this.opponentEngines[i][0].cardEngineTarget2=="Self"){
                if(this.opponentEngines[i][0].cardEngineType2=="Damage"){
                    if(this.opponentBoard[this.opponentEngines[i][1]].damageBondI){this.opponentBoard[this.opponentBoard[this.opponentEngines[i]].damageBondI].cardHealth -= this.opponentEngines[i][0].cardEngineValue2}
                    else if(this.opponentBoard[this.opponentEngines[i][1]].statusses[2].status=="Shield"){this.opponentBoard[this.opponentEngines[i][1]].statusses[2]={}}
                    else {
                        if(this.opponentEngines[i][1]!=9){if(this.opponentBoard[this.opponentEngines[i][1]+1].cardEffect!="Unkillable"){this.opponentBoard[this.opponentEngines[i][1]].cardHealth -= this.opponentEngines[i][0].cardEngineValue2}}
                        else{this.opponentBoard[this.opponentEngines[i][1]].cardHealth -= this.opponentEngines[i][0].cardEngineValue2}
                        if(this.oppChiefI!=null){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                        if(this.oppChiefI2!=null){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}
         } else if(this.opponentEngines[i][0].cardEngineType2=="Boost"){
                    this.opponentBoard[this.opponentEngines[i][1]].cardHealth += this.opponentEngines[i][0].cardEngineValue2
                    if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentEngines[i][0].cardEngineValue2}
                    if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentEngines[i][0].cardEngineValue2}}
            } else if(this.opponentEngines[i][0].cardEngineTarget2=="Left"){
                if(this.opponentEngines[i][0].cardEngineType2=="Boost"){
                    if(this.opponentEngines[i][1]!=0){if(this.opponentBoard[this.opponentEngines[i][1]-1].cardName){
                        this.opponentBoard[this.opponentEngines[i][1]-1].cardHealth += this.opponentEngines[i][0].cardEngineValue2
                        if(this.opponentBoard[this.opponentEngines[i][1]-1].cardEngineCondition=="Received Boost"){this.opponentBoard[this.opponentEngines[i][1]-1].cardEngineValue++}
                        if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentEngines[i][0].cardEngineValue2}
                        if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentEngines[i][0].cardEngineValue2}
                        }}}
           else if(this.opponentEngines[i][0].cardEngineType2=="Damage"){
                    if(this.opponentEngines[i][1]!=0){if(this.opponentBoard[this.opponentEngines[i][1]-1].cardName){
                      if(this.opponentBoard[this.opponentEngines[i][1]-1].damageBondI){this.opponentBoard[this.opponentBoard[this.opponentEngines[i]].damageBondI].cardHealth -= this.opponentEngines[i][0].cardEngineValue2}
                      else if(this.opponentBoard[this.opponentEngines[i][1]-1].statusses[2].status=="Shield"){this.opponentBoard[this.opponentEngines[i][1]-1].statusses[2]={}}
                      else {
                          this.opponentBoard[this.opponentEngines[i][1]-1].cardHealth -= this.opponentEngines[i][0].cardEngineValue2
                          if(this.opponentBoard[this.opponentEngines[i][1]-1].cardEngineCondition=="Damage Taken"){this.opponentBoard[this.opponentEngines[i][1]-1].cardEngineValue++}
                          if(this.oppChiefI!=null && this.opponentBoard[this.opponentEngines[i][1]-1].cardName){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                          if(this.oppChiefI2!=null && this.opponentBoard[this.opponentEngines[i][1]-1].cardName){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}}}}
            } else if(this.opponentEngines[i][0].cardEngineTarget2=="Right"){
                    if(this.opponentEngines[i][0].cardEngineType2=="Boost"){
                        if(this.opponentEngines[i][1]!=9){if(this.opponentBoard[this.opponentEngines[i][1]+1].cardName){
                            this.opponentBoard[this.opponentEngines[i][1]+1].cardHealth += this.opponentEngines[i][0].cardEngineValue2
                            if(this.opponentBoard[this.opponentEngines[i][1]+1].cardEngineCondition=="Received Boost"){this.opponentBoard[this.opponentEngines[i][1]+1].cardEngineValue++}
                            if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentEngines[i][0].cardEngineValue2}
                            if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentEngines[i][0].cardEngineValue2}}}
                } else if(this.opponentEngines[i][0].cardEngineType2=="Damage"){
                    if(this.opponentEngines[i][1]!=9){if(this.opponentBoard[this.opponentEngines[i][1]+1].cardName){
                      if(this.opponentBoard[this.opponentEngines[i][1]+1].damageBondI){
                        this.opponentBoard[this.opponentBoard[this.opponentEngines[i]].damageBondI].cardHealth -= this.opponentEngines[i][0].cardEngineValue2
                    } else if(this.opponentBoard[this.opponentEngines[i][1]+1].statusses[2].status=="Shield"){
                      this.opponentBoard[this.opponentEngines[i][1]+1].statusses[2]={}
                    } else {
                        if(this.opponentEngines[i][1]<8){if(this.opponentBoard[this.opponentEngines[i][1]+2].cardEffect!="Unkillable"){this.opponentBoard[this.opponentEngines[i][1]+1].cardHealth -= this.opponentEngines[i][0].cardEngineValue2}}
                        else{this.opponentBoard[this.opponentEngines[i][1]+1].cardHealth -= this.opponentEngines[i][0].cardEngineValue2}
                        if(this.opponentBoard[this.opponentEngines[i][1]+1].cardEngineCondition=="Damage Taken"){this.opponentBoard[this.opponentEngines[i][1]+1].cardEngineValue++}
                        if(this.oppChiefI!=null && this.opponentBoard[this.opponentEngines[i][1]+1].cardName){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                        if(this.oppChiefI2!=null && this.opponentBoard[this.opponentEngines[i][1]+1].cardName){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}}}}
            } else if(this.opponentEngines[i][0].cardEngineTarget2=="Adjacent"){
                if(this.opponentEngines[i][0].cardEngineType2=="Boost"){
                    if(this.opponentEngines[i][1]!=0){if(this.opponentBoard[this.opponentEngines[i][1]-1].cardName){
                        this.opponentBoard[this.opponentEngines[i][1]-1].cardHealth += this.opponentEngines[i][0].cardEngineValue2
                        if(this.opponentBoard[this.opponentEngines[i][1]-1].cardEngineCondition=="Received Boost"){this.opponentBoard[this.opponentEngines[i][1]-1].cardEngineValue++}
                        if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentEngines[i][0].cardEngineValue2}
                        if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentEngines[i][0].cardEngineValue2}
                        }}
                    if(this.opponentEngines[i][1]!=9){if(this.opponentBoard[this.opponentEngines[i][1]+1].cardName){
                        this.opponentBoard[this.opponentEngines[i][1]+1].cardHealth += this.opponentEngines[i][0].cardEngineValue2
                        if(this.opponentBoard[this.opponentEngines[i][1]+1].cardEngineCondition=="Received Boost"){this.opponentBoard[this.opponentEngines[i][1]+1].cardEngineValue++}
                        if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentEngines[i][0].cardEngineValue2}
                        if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentEngines[i][0].cardEngineValue2}
                        }}
                } else if(this.opponentEngines[i][0].cardEngineType2=="Damage"){
                    if(this.opponentEngines[i][1]!=0){if(this.opponentEngines[i][1]!=0){if(this.opponentBoard[this.opponentEngines[i][1]-1].cardName){
                      if(this.opponentBoard[this.opponentEngines[i][1]-1].damageBondI){this.opponentBoard[this.opponentBoard[this.opponentEngines[i][1]-1].damageBondI].cardHealth -= this.opponentEngines[i][0].cardEngineValue2}
                      else if(this.opponentBoard[this.opponentEngines[i][1]-1].statusses[2].status=="Shield"){this.opponentBoard[this.opponentEngines[i][1]-1].statusses[2]={}}
                      else {
                        this.opponentBoard[this.opponentEngines[i][1]-1].cardHealth -= this.opponentEngines[i][0].cardEngineValue2
                        if(this.opponentBoard[this.opponentEngines[i][1]-1].cardEngineCondition=="Damage Taken"){this.opponentBoard[this.opponentEngines[i][1]-1].cardEngineValue++}
                        if(this.oppChiefI!=null && this.opponentBoard[this.opponentEngines[i][1]-1].cardName){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                        if(this.oppChiefI2!=null && this.opponentBoard[this.opponentEngines[i][1]-1].cardName){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}
                }}}   if(this.opponentEngines[i][1]!=9){if(this.opponentBoard[this.opponentEngines[i][1]+1].cardName){
                      if(this.opponentBoard[this.opponentEngines[i][1]+1].damageBondI){this.opponentBoard[this.opponentBoard[this.opponentEngines[i][1]+1].damageBondI].cardHealth -= this.opponentEngines[i][0].cardEngineValue2}
                      else if(this.opponentBoard[this.opponentEngines[i][1]+1].statusses[2].status=="Shield"){this.opponentBoard[this.opponentEngines[i][1]+1].statusses[2]={}}
                      else {
                        if(this.opponentEngines[i][1]<8){if(this.opponentBoard[this.opponentEngines[i][1]+2].cardEffect!="Unkillable"){this.opponentBoard[this.opponentEngines[i][1]+1].cardHealth -= this.opponentEngines[i][0].cardEngineValue2}}
                        else{this.opponentBoard[this.opponentEngines[i][1]+1].cardHealth -= this.opponentEngines[i][0].cardEngineValue2}
                        if(this.opponentBoard[this.opponentEngines[i][1]+1].cardEngineCondition=="Damage Taken"){this.opponentBoard[this.opponentEngines[i][1]+1].cardEngineValue++}
                        if(this.oppChiefI!=null && this.opponentBoard[this.opponentEngines[i][1]+1].cardName){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                        if(this.oppChiefI2!=null && this.opponentBoard[this.opponentEngines[i][1]+1].cardName){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}
                }}}
            } else if(this.opponentEngines[i][0].cardEngineTarget2=="Random"){
                if(this.opponentEngines[i][0].cardTargetUnitType2=="Ally"){
                    if(this.opponentEngines[i][0].cardEngineType2=="Boost"){
                        if(this.filledOpponentBoardSpace.length>0){
                            let unit = this.opponentBoard[this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]]
                            unit.cardHealth += this.opponentEngines[i][0].cardEngineValue2
                            if(unit.cardEngineCondition=="Received Boost"){unit.cardEngineValue++}
                            if(this.spyI!=null) {this.playerBoard[this.spyI].cardHealth += this.opponentEngines[i][0].cardEngineValue2}
                            if(this.spyI2!=null) {this.playerBoard[this.spyI2].cardHealth += this.opponentEngines[i][0].cardEngineValue2}
                            }
             } else if(this.opponentEngines[i][0].cardEngineType2=="Damage"){
                        if(this.filledOpponentBoardSpace.length>0){
                          let unitI = this.filledOpponentBoardSpace[Math.floor(Math.random() * this.filledOpponentBoardSpace.length)]
                            if(this.opponentBoard[unitI].damageBondI) {this.opponentBoard[this.opponentBoard[unitI].damageBondI] -= this.opponentEngines[i][0].cardEngineValue2}
                            else if(this.opponentBoard[unitI].statusses[2].status=="Shield"){this.opponentBoard[unitI].statusses[2]={}}
                              else {
                              if(unitI!=9){if(this.opponentBoard[unitI+1].cardEffect!="Unkillable"){this.opponentBoard[unitI].cardHealth -= this.opponentEngines[i][0].cardEngineValue2}}
                              else{this.opponentBoard[unitI].cardHealth -= this.opponentEngines[i][0].cardEngineValue2}
                              if(this.opponentBoard[unitI].cardEngineCondition=="Damage Taken"){this.opponentBoard[unitI].cardEngineValue++}
                            }
                              if(this.oppChiefI!=null && this.opponentBoard[unitI].cardName){this.opponentBoard[this.oppChiefI].cardEngineValue++}
                              if(this.oppChiefI2!=null && this.opponentBoard[unitI].cardName){this.opponentBoard[this.oppChiefI2].cardEngineValue++}}
                    }
            }   else if(this.opponentEngines[i][0].cardTargetUnitType2=="Enemy"){
                    if(this.opponentEngines[i][0].cardEngineType2=="Boost"){
                        if(this.filledBoardSpace.length>0){
                            let unit = this.playerBoard[this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]]
                            unit.cardHealth += this.opponentEngines[i][0].cardEngineValue2
                            if(unit.cardEngineCondition=="Received Boost"){unit.cardEngineValue++}
                            if(this.oppSpyI!=null) {this.opponentBoard[this.oppSpyI].cardHealth += this.opponentEngines[i][0].cardEngineValue2}
                            if(this.oppSpyI2!=null) {this.opponentBoard[this.oppSpyI2].cardHealth += this.opponentEngines[i][0].cardEngineValue2}
                        }
             } else if(this.opponentEngines[i][0].cardEngineType2=="Damage"){
                        if(this.filledBoardSpace.length>0){
                            let unitI = this.filledBoardSpace[Math.floor(Math.random() * this.filledBoardSpace.length)]
                            if(this.playerBoard[unitI].damageBondI) {this.playerBoard[this.playerBoard[unitI].damageBondI] -= this.opponentEngines[i][0].cardEngineValue2}
                            else if(this.playerBoard[unitI].statusses[2].status=="Shield"){this.playerBoard[unitI].statusses[2]={}}
                              else {
                              if(unitI!=9){if(this.opponentBoard[unitI+1].cardEffect!="Unkillable"){this.playerBoard[unitI].cardHealth -= this.opponentEngines[i][0].cardEngineValue2}}
                              else{this.playerBoard[unitI].cardHealth -= this.opponentEngines[i][0].cardEngineValue2}
                              if(this.playerBoard[unitI].cardEngineCondition=="Damage Taken"){this.playerBoard[unitI].cardEngineValue++}
                              if(this.chiefI!=null && this.playerBoard[unitI].cardName){this.playerBoard[this.chiefI].cardEngineValue++}
                              if(this.chiefI2!=null && this.playerBoard[unitI].cardName){this.playerBoard[this.chiefI2].cardEngineValue++}}
                    }
                }
                if(this.opponentEngines[i][0].cardEngineCondition2=="Damage Taken" || this.opponentEngines[i][0].cardEngineCondition2=="Received Boost" || this.opponentEngines[i][0].cardEngineCondition2=="Allied Unit Damaged"){this.opponentEngines[i][0].cardEngineValue2=0}}
            }
            }, 200)
          }}, 100)}
      },
      processStatus(){
          for(let i = 0; i < this.filledBoardSpace.length; i++){if(this.playerBoard[this.filledBoardSpace[i]].cardName==undefined){this.filledBoardSpace.splice(i, 1)}}
          for (let i = 0; i < this.filledBoardSpace.length; i++){
              if(this.playerBoard[this.filledBoardSpace[i]].statusses[0].status) {this.playerBoard[this.filledBoardSpace[i]].cardHealth--; this.playerBoard[this.filledBoardSpace[i]].statusses[0].duration--}
              if(this.playerBoard[this.filledBoardSpace[i]].statusses[1].status) {this.playerBoard[this.filledBoardSpace[i]].cardHealth++; this.playerBoard[this.filledBoardSpace[i]].statusses[1].duration--}
              if(this.playerBoard[this.filledBoardSpace[i]].statusses[0].duration==0) {this.playerBoard[this.filledBoardSpace[i]].statusses[0]={}}
              if(this.playerBoard[this.filledBoardSpace[i]].statusses[1].duration==0) {this.playerBoard[this.filledBoardSpace[i]].statusses[1]={}}
              if(this.playerBoard[this.filledBoardSpace[i]].damageBondI){if(this.playerBoard[this.playerBoard[this.filledBoardSpace[i]].damageBondI].cardName==null){delete this.playerBoard[this.filledBoardSpace[i]].damageBondI}}
          }
          if(this.oppSpyI!=null && this.opponentBoard[this.oppSpyI].statusses[3].status){this.oppSpyI = null}
          if(this.oppSpy2!=null && this.opponentBoard[this.oppSpyI2].statusses[3].status){this.oppSpyI2 = null}
          if(this.oppChiefI!=null && this.opponentBoard[this.oppChiefI].statusses[3].status){this.oppChiefI = null}
          if(this.oppChiefI2!=null && this.opponentBoard[this.oppChiefI2].statusses[3].status){this.oppChiefI2 = null}
      },
      processEnemyStatus(){
          for(let i = 0; i < this.filledOpponentBoardSpace.length; i++){if(this.opponentBoard[this.filledOpponentBoardSpace[i]].cardName==undefined){this.filledOpponentBoardSpace.splice(i, 1)}}
          for (let i = 0; i < this.filledOpponentBoardSpace.length; i++){
              if(this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0].status) {this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth--; this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0].duration--}
              if(this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1].status) {this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth++; this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1].duration--}
              if(this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0].duration==0) {this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[0]={}}
              if(this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1].duration==0) {this.opponentBoard[this.filledOpponentBoardSpace[i]].statusses[1]={}}
          }
          if(this.spyI!=null && this.playerBoard[this.spyI].statusses[3].status){this.spyI = null}
          if(this.spyI2!=null && this.playerBoard[this.spyI2].statusses[3].status){this.spyI2 = null}
          if(this.chiefI!=null && this.playerBoard[this.chiefI].statusses[3].status){this.chiefI = null}
          if(this.chiefI2!=null && this.playerBoard[this.chiefI2].statusses[3].status){this.chiefI2 = null}
      },
      countPoints(){
          let score = 0
          for (let i = 0; i < this.filledBoardSpace.length; i++){
              score += this.playerBoard[this.filledBoardSpace[i]].cardHealth
          }
          this.playerScore = score;
          let opponentScore = 0
          for (let i = 0; i < this.filledOpponentBoardSpace.length; i++){
              opponentScore += this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth
          }
          this.opponentScore = opponentScore;
      },
      checkDeath(){
          if(this.chiefI!=null){if(this.playerBoard[this.chiefI].cardHealth<1){this.chiefI=null}}
          if(this.chiefI2!=null){if(this.playerBoard[this.chiefI2].cardHealth<1){this.chiefI2=null}}
          if(this.spyI!=null){if(this.playerBoard[this.spyI].cardHealth<1){this.spyI=null}}
          if(this.spyI2!=null){if(this.playerBoard[this.spyI2].cardHealth<1){this.spyI2=null}}
          if(this.oppChiefI!=null){if(this.opponentBoard[this.oppChiefI].cardHealth<1){this.oppChiefI=null}}
          if(this.oppChiefI2!=null){if(this.opponentBoard[this.oppChiefI2].cardHealth<1){this.oppChiefI2=null}}
          if(this.oppSpyI!=null){if(this.opponentBoard[this.oppSpyI].cardHealth<1){this.oppSpyI=null}}
          if(this.oppSpyI2!=null){if(this.opponentBoard[this.oppSpyI2].cardHealth<1){this.oppSpyI2=null}}
          for (let i = 0; i < 10; i++){
            if(this.playerBoard[i].cardName!=undefined){
                if(this.playerBoard[i].cardHealth<1) {
                    if(this.playerBoard[i].cardEffect=="Engine"){
                        for(let o = 0; o < this.alliedEngines.length; o++){
                            if(this.alliedEngines[o][1]==i){
                                this.alliedEngines.splice(o, 1)
                            }
                        }
                    }
                    this.playerGraveyard.push(this.playerBoard[i])
                    this.playerBoard[i]={}
                    for(let o = 0; o < this.filledBoardSpace.length; o++){
                            if(this.filledBoardSpace[o]==i){
                                this.filledBoardSpace.splice(o, 1)
                            }
                    }
            }}
          }
          for (let i = 0; i < 10; i++){
            if(this.opponentBoard[i].cardName!=undefined){
                if(this.opponentBoard[i].cardHealth<1) {
                    if(this.opponentBoard[i].cardEffect=="Engine"){
                        for(let o = 0; o < this.opponentEngines.length; o++){
                            if(this.opponentEngines[o][1]==i){
                                this.opponentEngines.splice(o, 1)
                            }
                        }
                    }
                    this.opponentGraveyard.push(this.opponentBoard[i])
                    this.opponentBoard[i]={}
                    for(let o = 0; o < this.filledOpponentBoardSpace.length; o++){
                            if(this.filledOpponentBoardSpace[o]==i){
                                this.filledOpponentBoardSpace.splice(o, 1)
                            }
                    }
            }}
          }
      },
      discardCard(){
        this.chosenCardTarget=""
        this.chosenCardPlayedCard=""
        this.chosenCardTargetType=""
        this.showTutoredCard=false
        this.chosenPlayableCard.statusses = [{}, {}, {}, {}]
        this.playerGraveyard.push(this.chosenPlayableCard);
        this.playerHand[this.chosenPlayableCardIndex]={};
        this.chosenCard={};
        this.chosenPlayableCard={};
        this.showTutoredCard=false
        this.countPoints();
        this.processEngines();
        this.processStatus();
        this.cardPlayed = true
        this.checkDeath();
      },
      discardEnemyCard(){
        console.log("Enemy Discard")
        this.chosenEnemyPlayableCard.statusses = [{}, {}, {}, {}]
        this.opponentGraveyard.push(this.chosenEnemyPlayableCard);
        this.opponentHand[this.chosenEnemyPlayableCardIndex]={};
        this.chosenEnemyCard={};
        this.chosenEnemyPlayableCard=null;
        this.showTutoredCard=false
      },
      checkRoundEnd(){
          console.log("Checking round end")
          if(this.playerPassed && !this.opponentPassed){this.startEnemyTurn()}
          if(this.playerPassed && this.opponentPassed){
              if(this.playerScore > this.opponentScore){
                  if(this.playerWonRound==true){this.playerWon=true}
                  else{this.playerWonRound=true; this.playerStarts=true}
              }
              else if(this.playerScore < this.opponentScore){
                  if(this.opponentWonRound==true){this.opponentWon=true}
                  else{this.opponentWonRound=true; this.playerStarts=false}
              }
              else {
                  if(this.playerWonRound==true){this.playerWon=true}
                  else{this.playerWonRound=true; this.playerStarts=true}
                  if(this.opponentWonRound==true){this.opponentWon=true}
                  else{this.opponentWonRound=true}
              }
              if(!this.playerWon && !this.opponentWon){this.startNewRound()}
              else{  
                if(this.playerWon && this.opponentWon){this.gameResult="Draw"}
                else if(this.playerWon){this.gameResult="Victory"}
                else {this.gameResult="Defeat"}
          }}
      },
      startNewRound(){
          this.playerPassed = false;
          this.opponentPassed = false;
          this.isEnemyTurn = true; 
          this.playerPlayed = true;
          this.playerScore = 0;
          this.opponentScore = 0;
          for(let i = 0; i < 10; i++){
              if(this.playerBoard[i].cardName!=undefined){
                if(this.playerBoard[i].cardEffect=="Engine"){
                    for(let o = 0; o < this.alliedEngines.length; o++){
                    if(this.alliedEngines[o][1]==i){
                        this.alliedEngines.splice(o, 1)
                    }
                    }
                }
                this.playerGraveyard.push(this.playerBoard[i])
                this.playerBoard[i]={}
                for(let o = 0; o < this.filledBoardSpace.length; o++){
                    if(this.filledBoardSpace[o]==i){
                        this.filledBoardSpace.splice(o, 1)
                    }
                }
              }
          }
          for(let i = 0; i < 10; i++){
              if(this.opponentBoard[i].cardName!=undefined){
                    if(this.opponentBoard[i].cardEffect=="Engine"){
                        for(let o = 0; o < this.opponentEngines.length; o++){
                            if(this.opponentEngines[o][1]==i){
                                this.opponentEngines.splice(o, 1)
                            }
                        }
                    }
                    this.opponentGraveyard.push(this.opponentBoard[i])
                    this.opponentBoard[i]={}
                    for(let o = 0; o < this.filledOpponentBoardSpace.length; o++){
                        if(this.filledOpponentBoardSpace[o]==i){
                            this.filledOpponentBoardSpace.splice(o, 1)
                        }
                    }
            }
          }
          for(let i = 0; i < this.filledBoardSpace.length; i++){
              console.log(`${this.playerBoard[this.filledBoardSpace[i]].cardName} health: ${this.playerBoard[this.filledBoardSpace[i]].cardHealth}`)
          }
          for(let i = 0; i < this.filledOpponentBoardSpace.length; i++){
              console.log(`${this.opponentBoard[this.filledOpponentBoardSpace[i]].cardName} health: ${this.opponentBoard[this.filledOpponentBoardSpace[i]].cardHealth}`)
          }
          let emptyHandSpots = [];
          let emptyOpponentHandSpots = [];
          for(let i = 0; i < 10; i++){
              if(this.playerHand[i].cardName==undefined){emptyHandSpots.push(i)}
          }
          for(let i = 0; i < 2; i++){
              if(emptyHandSpots.length){  
                let drawnCard = this.playerDeck.shift()
                drawnCard.revealed1 = false
                drawnCard.revealed2 = false
                drawnCard.revealed3 = false
                drawnCard.revealed4 = false
                if(drawnCard.revealedCount){drawnCard.revealedCount++}
                else{drawnCard.revealedCount=1}
                let chosenRevealed = null
                if(drawnCard.revealedCount==1){chosenRevealed=drawnCard.revealed1}
                else if(drawnCard.revealedCount==2){chosenRevealed=drawnCard.revealed2}
                else if(drawnCard.revealedCount==3){chosenRevealed=drawnCard.revealed3}
                else {chosenRevealed=drawnCard.revealed4}
                if(this.playerDeck.length){  
                    this.playerHand[emptyHandSpots[0]] = {
                        cardName: drawnCard.cardName,
                        cardBaseHealth: drawnCard.cardBaseHealth,
                        cardEffect: drawnCard.cardEffect,
                        cardEffectCondition: drawnCard.cardEffectCondition,
                        cardEffectTarget: drawnCard.cardEffectTarget,
                        cardStatus: drawnCard.cardStatus,
                        cardStatus2: drawnCard.cardStatus2,
                        cardStatusDuration: drawnCard.cardStatusDuration,
                        cardStatusDuration2: drawnCard.cardStatusDuration2,
                        cardTargetUnitType: drawnCard.cardTargetUnitType,
                        cardTargetUnitType2: drawnCard.cardTargetUnitType2,
                        cardEffectValue: drawnCard.cardEffectValue,
                        cardEffect2: drawnCard.cardEffect2,
                        cardEffectTarget2: drawnCard.cardEffectTarget2,
                        cardEffectValue2: drawnCard.cardEffectValue2,
                        cardEngineType: drawnCard.cardEngineType,
                        cardEngineTarget: drawnCard.cardEngineTarget,
                        cardEngineValue: drawnCard.cardEngineValue,
                        cardEngineCondition: drawnCard.cardEngineCondition,
                        cardEngineType2: drawnCard.cardEngineType2,
                        cardEngineTarget2: drawnCard.cardEngineTarget2,
                        cardEngineValue2: drawnCard.cardEngineValue2,
                        cardEngineCondition2: drawnCard.cardEngineCondition2,
                        cardRandomness1: drawnCard.cardRandomness1,
                        cardRandomness2: drawnCard.cardRandomness2,
                        cardRemovalCondition: drawnCard.cardRemovalCondition,
                        cardRemovalConditionValue: drawnCard.cardRemovalConditionValue,
                        playedCard: drawnCard.playedCard,
                        consumeType: drawnCard.consumeType,
                        cardRarity: drawnCard.cardRarity,
                        cardDescription: drawnCard.cardDescription,
                        revealed: chosenRevealed,
                }}
                emptyHandSpots.shift();
          }}
          for(let i = 0; i < 10; i++){
              if(this.opponentHand[i].cardName==undefined){emptyOpponentHandSpots.push(i)}
          }
          for(let i = 0; i < 2; i++){
              if(emptyOpponentHandSpots.length){  
                let drawnCard = this.opponentDeck.shift()
                drawnCard.revealed1 = false
                drawnCard.revealed2 = false
                drawnCard.revealed3 = false
                drawnCard.revealed4 = false
                if(drawnCard.revealedCount){drawnCard.revealedCount++}
                else{drawnCard.revealedCount=1}
                let chosenRevealed = null
                if(drawnCard.revealedCount==1){chosenRevealed=drawnCard.revealed1}
                else if(drawnCard.revealedCount==2){chosenRevealed=drawnCard.revealed2}
                else if(drawnCard.revealedCount==3){chosenRevealed=drawnCard.revealed3}
                else {chosenRevealed=drawnCard.revealed4}
                if(this.opponentDeck.length){  
                    this.opponentHand[emptyOpponentHandSpots[0]] = {
                        cardName: drawnCard.cardName,
                        cardBaseHealth: drawnCard.cardBaseHealth,
                        cardEffect: drawnCard.cardEffect,
                        cardEffectCondition: drawnCard.cardEffectCondition,
                        cardEffectTarget: drawnCard.cardEffectTarget,
                        cardStatus: drawnCard.cardStatus,
                        cardStatus2: drawnCard.cardStatus2,
                        cardStatusDuration: drawnCard.cardStatusDuration,
                        cardStatusDuration2: drawnCard.cardStatusDuration2,
                        cardTargetUnitType: drawnCard.cardTargetUnitType,
                        cardTargetUnitType2: drawnCard.cardTargetUnitType2,
                        cardEffectValue: drawnCard.cardEffectValue,
                        cardEffect2: drawnCard.cardEffect2,
                        cardEffectTarget2: drawnCard.cardEffectTarget2,
                        cardEffectValue2: drawnCard.cardEffectValue2,
                        cardEngineType: drawnCard.cardEngineType,
                        cardEngineTarget: drawnCard.cardEngineTarget,
                        cardEngineValue: drawnCard.cardEngineValue,
                        cardEngineCondition: drawnCard.cardEngineCondition,
                        cardEngineType2: drawnCard.cardEngineType2,
                        cardEngineTarget2: drawnCard.cardEngineTarget2,
                        cardEngineValue2: drawnCard.cardEngineValue2,
                        cardEngineCondition2: drawnCard.cardEngineCondition2,
                        cardRandomness1: drawnCard.cardRandomness1,
                        cardRandomness2: drawnCard.cardRandomness2,
                        cardRemovalCondition: drawnCard.cardRemovalCondition,
                        cardRemovalConditionValue: drawnCard.cardRemovalConditionValue,
                        playedCard: drawnCard.playedCard,
                        consumeType: drawnCard.consumeType,
                        cardRarity: drawnCard.cardRarity,
                        cardDescription: drawnCard.cardDescription,
                        revealed: chosenRevealed,
                }}
                emptyOpponentHandSpots.shift();
          }
          }
          this.spyI=null;
          this.spyI2=null;
          this.oppSpyI=null;
          this.oppSpyI2=null;
          this.chiefI=null;
          this.chiefI2=null;
          this.oppChiefI=null;
          this.oppChiefI2=null;
          this.alliedEngines=[];
          this.opponentEngines=[];
          this.filledBoardSpace=[];
          this.filledOpponentBoardSpace=[];
          console.log(`Player starts: ${this.playerStarts}`)
          this.isRedrawPhase = true
      },
      confirmRedraw(){
        for(let i = 0; i < this.redrawnCards.length; i++){
            let drawnCard = this.playerDeck.shift()
            drawnCard.revealed1 = false
            drawnCard.revealed2 = false
            drawnCard.revealed3 = false
            drawnCard.revealed4 = false
            if(drawnCard.revealedCount){drawnCard.revealedCount++}
            else{drawnCard.revealedCount=1}
            let chosenRevealed = null
            if(drawnCard.revealedCount==1){chosenRevealed=drawnCard.revealed1}
            else if(drawnCard.revealedCount==2){chosenRevealed=drawnCard.revealed2}
            else if(drawnCard.revealedCount==3){chosenRevealed=drawnCard.revealed3}
            else {chosenRevealed=drawnCard.revealed4}
            this.playerDeck.splice(Math.floor(Math.random()*this.playerDeck.length), 0, this.playerHand[this.redrawnCards[i]]) 
            this.playerHand[this.redrawnCards[i]] = {
                    cardName: drawnCard.cardName,
                    cardBaseHealth: drawnCard.cardBaseHealth,
                    cardEffect: drawnCard.cardEffect,
                    cardEffectCondition: drawnCard.cardEffectCondition,
                    cardEffectTarget: drawnCard.cardEffectTarget,
                    cardStatus: drawnCard.cardStatus,
                    cardStatus2: drawnCard.cardStatus2,
                    cardStatusDuration: drawnCard.cardStatusDuration,
                    cardStatusDuration2: drawnCard.cardStatusDuration2,
                    cardTargetUnitType: drawnCard.cardTargetUnitType,
                    cardTargetUnitType2: drawnCard.cardTargetUnitType2,
                    cardEffectValue: drawnCard.cardEffectValue,
                    cardEffect2: drawnCard.cardEffect2,
                    cardEffectTarget2: drawnCard.cardEffectTarget2,
                    cardEffectValue2: drawnCard.cardEffectValue2,
                    cardEngineType: drawnCard.cardEngineType,
                    cardEngineTarget: drawnCard.cardEngineTarget,
                    cardEngineValue: drawnCard.cardEngineValue,
                    cardEngineCondition: drawnCard.cardEngineCondition,
                    cardEngineType2: drawnCard.cardEngineType2,
                    cardEngineTarget2: drawnCard.cardEngineTarget2,
                    cardEngineValue2: drawnCard.cardEngineValue2,
                    cardEngineCondition2: drawnCard.cardEngineCondition2,
                    cardRandomness1: drawnCard.cardRandomness1,
                    cardRandomness2: drawnCard.cardRandomness2,
                    cardRemovalCondition: drawnCard.cardRemovalCondition,
                    cardRemovalConditionValue: drawnCard.cardRemovalConditionValue,
                    playedCard: drawnCard.playedCard,
                    consumeType: drawnCard.consumeType,
                    cardRarity: drawnCard.cardRarity,
                    cardDescription: drawnCard.cardDescription,
                    revealed: chosenRevealed,
            }
        }
        let opponentRedrawnCards = []
        for(let i = 0; i < 10; i++){
            if(this.opponentHand[i].cardRarity=="Bronze"){opponentRedrawnCards.push(i)}
            if(opponentRedrawnCards.length>1){break}
        }
        for(let i = 0; i < opponentRedrawnCards.length; i++){
            let drawnCard = this.opponentDeck.shift()
            drawnCard.revealed1 = false
            drawnCard.revealed2 = false
            drawnCard.revealed3 = false
            drawnCard.revealed4 = false
            if(drawnCard.revealedCount){drawnCard.revealedCount++}
            else{drawnCard.revealedCount=1}
            let chosenRevealed = null
            if(drawnCard.revealedCount==1){chosenRevealed=drawnCard.revealed1}
            else if(drawnCard.revealedCount==2){chosenRevealed=drawnCard.revealed2}
            else if(drawnCard.revealedCount==3){chosenRevealed=drawnCard.revealed3}
            else {chosenRevealed=drawnCard.revealed4}
            this.opponentDeck.splice(Math.floor(Math.random()*this.opponentDeck.length), 0, this.opponentHand[opponentRedrawnCards[i]]) 
            this.opponentHand[opponentRedrawnCards[i]] = {
                    cardName: drawnCard.cardName,
                    cardBaseHealth: drawnCard.cardBaseHealth,
                    cardEffect: drawnCard.cardEffect,
                    cardEffectCondition: drawnCard.cardEffectCondition,
                    cardEffectTarget: drawnCard.cardEffectTarget,
                    cardStatus: drawnCard.cardStatus,
                    cardStatus2: drawnCard.cardStatus2,
                    cardStatusDuration: drawnCard.cardStatusDuration,
                    cardStatusDuration2: drawnCard.cardStatusDuration2,
                    cardTargetUnitType: drawnCard.cardTargetUnitType,
                    cardTargetUnitType2: drawnCard.cardTargetUnitType2,
                    cardEffectValue: drawnCard.cardEffectValue,
                    cardEffect2: drawnCard.cardEffect2,
                    cardEffectTarget2: drawnCard.cardEffectTarget2,
                    cardEffectValue2: drawnCard.cardEffectValue2,
                    cardEngineType: drawnCard.cardEngineType,
                    cardEngineTarget: drawnCard.cardEngineTarget,
                    cardEngineValue: drawnCard.cardEngineValue,
                    cardEngineCondition: drawnCard.cardEngineCondition,
                    cardEngineType2: drawnCard.cardEngineType2,
                    cardEngineTarget2: drawnCard.cardEngineTarget2,
                    cardEngineValue2: drawnCard.cardEngineValue2,
                    cardEngineCondition2: drawnCard.cardEngineCondition2,
                    cardRandomness1: drawnCard.cardRandomness1,
                    cardRandomness2: drawnCard.cardRandomness2,
                    cardRemovalCondition: drawnCard.cardRemovalCondition,
                    cardRemovalConditionValue: drawnCard.cardRemovalConditionValue,
                    playedCard: drawnCard.playedCard,
                    consumeType: drawnCard.consumeType,
                    cardRarity: drawnCard.cardRarity,
                    cardDescription: drawnCard.cardDescription,
                    revealed: chosenRevealed,
            }
        }
        this.isRedrawPhase = false
        this.redrawnCards = []
        this.chosenCard = {}
        if(!this.playerStarts){this.isEnemyTurn = true; this.playerPlayed = true; console.log("Opponent went first"); this.startEnemyTurn()}
        else{this.isEnemyTurn = false; this.playerPlayed = false}
      },
  }
}
// 
</script>

<style>
.circle {
  height: 4vh;
  width: 4vh;
  background-color: #bbb;
  border-radius: 50%;
}
.vertical {
  display: inline-block;
  border-left: 1px solid black;
  margin: 0 10px;
}
</style>
