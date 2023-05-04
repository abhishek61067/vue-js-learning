<script>
export default {
  data() {
    return {
      question: '',
      answer: 'Questions usually contain a question mark. ;-)'
    }
  },
  watch: {
    // whenever question changes, this function will run
    
    question(newQ, oldQuestion) {
      // alert("test")
        if(this.question === ""){
            console.log("input is empty");
            return;
        }

        if(!(newQ.split("a").length > 1)){
             alert("I can guess that you didnt type a")
             this.question = "";
        }
        if (newQ.split("a").length > 1) {
                alert("I can guess that you have typed a")
        console.log(newQ.split("a").length);
                     this.question = "";

      }
      
    // console.log(newQ.split("a"));
    }
  },
  
}
</script>

<template>
        <p class="h2 text-primary">Watchers</p>  
    <div class="text-secondary h4">letter guessing game:
</div>
    Type some letter and i will guess the result:
    <input v-model="question" />
  <p>{{ question }}</p>
</template>