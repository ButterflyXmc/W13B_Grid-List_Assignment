<template>
  <div>
    <header>
      <h1>
        Tweets
        <img
          src="https://cdn-icons-png.flaticon.com/512/733/733579.png"
          alt="tweeter logo"
        />
      </h1>
      <!--5. This button will change the view as per the user's need -->
      <button @click="toggleButton">Change the display!</button>
    </header>
    <!--6. Variable name "list" should trigger if true or false -->
    <!-- TENARY SYNTAX "(condition) ? trueMode : falseMode"-->
    <!-- If list boolean is true, list-mode gets activated, and if it's false, grid-mode gets activated. Altough the website loads in list-mode because I've set the boolean to be true.  -->
    <div class="list" :class="list ? 'list-mode' : 'grid-mode'">
      <!--2. My tweet content will print in this main section -->
      <!-- <div v-for="(tweet, index) in tweets" :key="index"> -->
      <!-- the above code or ↓ does the same thing-->
      <div class="style" v-for="tweet in tweets" :key="tweet">
        <p>
          <b>{{ tweet.tweet }}</b>
        </p>
        <p>
          <i>
            {{ tweet.user }}
            <br />
            created in : {{ tweet.date }}
          </i>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TweetsComponent",
  data() {
    return {
      //3. The page will load in list-mode because I've set the boolean to be true
      list: true,
      //1. Adding an array that contains tweets, users and dates
      tweets: [
        {
          tweet:
            "At the gym I said subscription instead of membership and the girl replied 'lol this isn't a pharmacy'. Girl that's a prescription, we're both stupid LOL.",
          user: "@ahaamina",
          date: "Aug 15, 2018",
        },
        {
          tweet:
            "I was drinking on a tuesday and some guy said 'It's a tuesday, why are you drinking?' like boy, my vibes don't check the calender, it's good vibes here 24/7.",
          user: "@rennu",
          date: "May 11, 2020",
        },
        {
          tweet:
            "Sick of having to go to 2 different huts to buy pizza & sunglasses.",
          user: "@Leemanish",
          date: "Mar 24, 2013",
        },
        {
          tweet: "Been on hold so long I can't remember who I called.",
          user: "@fireland",
          date: "Jun 30, 2009",
        },
        {
          tweet:
            "I keep a baseball bat under my bed in case someone tries to break in and pitch a no hitter.",
          user: "@sagekol",
          date: "Jun 5, 2014",
        },
      ],
    };
  },
  // METHOD
  methods: {
    toggleButton() {
      //4. Flipping a boolean
      this.list = !this.list;
    },
  },
};
</script>


<style scoped>
header {
  display: grid;
  grid-template-columns: 1fr 0.6fr;
}

h1 {
  font-size: 6em;
  justify-self: end;
}

button {
  font-size: 1em;
  justify-self: end;
  align-self: center;
  padding: 20px;
  background-color: rgb(112, 193, 231);
  border: white solid 10px;
  border-radius: 20px;
  box-shadow: 15px 20px 50px rgb(13, 13, 132);
}

button:hover {
  transform: scale(0.9);
}

img {
  height: 60px;
}

.style {
  border: white 5px dashed;
  margin: 20px;
  background-color: rgba(101, 169, 224, 0.614);
  padding: 10px;
}

.list-mode {
  max-width: 30%;
  position: relative;
  left: 50%;
  transform: translate(-50%);
  font-size: 1.2em;
  background-color: rgba(63, 149, 175, 0.402);
  padding: 2%;
  border: 10px solid white;
}

.grid-mode {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
  background-color: rgba(92, 173, 86, 0.295);
  border: solid white 15px;
  padding: 2%;
  font-size: 1.3em;
}
</style>