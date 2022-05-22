<script>
import { Button } from 'attractions';
import { Card } from 'attractions';

let hasSubmitted=false;
let activeQuestion = 0;
let score = 0;
let myA=["option2", "option3", "option3"];
let myC=" ";

const questions  = [
        
        {que: "What is sin30",
            id: 1,
            options: [{
                title: "0",
                value: "option1"
            }, {
                title: "1/2",
                value: "option2"
            },
            {
                title: "1",
                value: "option3"
            }]
    
        }, 


        {que: "What is electron?",
            id: 2,
            options: [{
                title: "Movie",
                value: "option1"
            }, {
                title: "Sports",
                value: "option2"
            },
            {
                title: "A particle in Nucleaus",
                value: "option3"
            }]
    
        }, 
        
        
        {que: "Father of Nation",
            id: 3,
            options: [{
                title: "Nehru",
                value: "option1"
            }, {
                title: "Tilak",
                value: "option2"
            },
            {
                title: "Bapu",
                value: "option3"
            }]
        }
    
    ];

$: question= questions[activeQuestion];

	function inc() {
		if (activeQuestion === (questions.length - 1)) { return }
		
      if(myA[activeQuestion]===myC) {
   
    score=score+1;
      }
    activeQuestion += 1
	}


    function nSubmit() {
        if(myA[activeQuestion]===myC) {
   
    score=score+1;
      }

        hasSubmitted=true;
        console.log(score)
    }

    function reset() {
        activeQuestion=0;
        hasSubmitted=false;
        score=0;
    }



	let answers = Array(2).fill("");
</script>


<div class="quiz-container">
   
<Card>
     {#if !hasSubmitted}
     <div class="option-container">
<h3>{question.que}</h3>
{#each question.options as option (option.value)}
	<label>
		<input type="radio" 
					 bind:group={myC}
					 value={option.value}
									
					 /> 
		{option.title}
	</label>
    <br>
    <br>
    <br>
{/each}

    </div>

<div class="button-container">
<Button filled on:click={inc}>Next</Button>

<Button selected>Score: {score}/3</Button>


<Button filled on:click={nSubmit}>Submit</Button>
</div>

{:else}

Your Score is : <strong>{score}/3</strong>
<br><br>
<Button filled on:click={reset}>Reset</Button>

{/if}

</Card>



</div>


<style>
.button-container{
      display: flex;
      justify-content: space-around;
      
    }

    .quiz-container{
        
        justify-items: center;
        text-align: center;
        margin: 0 25%;
      
    }

    .option-container{
        
       text-align: left;
       margin: 10% 10% 10% 40%;
        
      
    }

</style>