<template>
    <div>
        <header>
            <h4> Question 1/3 </h4>
            <div class="bar">
                <div class="completion">

                </div>
            </div>
        </header>
        <div>
            <div class="qusetion-container">
                <h1 class="question">
                    something
                </h1>
            </div>
            <div class="options-container">
                <div class="option">
                    <p class="option-label">A</p>
                    <div class="option-value">
                        <p>Nacl</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>


<style scoped>

    header{
        margin-top: 20px;    
    }

    header h3 {
        font-size: 30px;
    }

    .bar{
        width: 300px;
        height: 50px;
        border: 3px solid blueviolet;
    }

    .completion {
        height: 100%;
        width: 0%;
        background-color: blueviolet;
    }

    .question-container {
        margin-top: 20px;
    }

    .question{
        font-size: 40px;
        margin-bottom: 20px;
    }

    .option {
        display: flex;
        margin-bottom: 20px;
        cursor: pointer;    
    }

    .option-label {
        display: flex;
        font-size: 30px;
        cursor: pointer;    
        background-color: blueviolet;
        width: 50px;
        height: 50px;
        align-items: center;
        justify-content: center;
        border-radius: 5px;
        color: azure;
    }

    .option-value {
        margin-top: 30px;
        background-color: aliceblue;
        width:  100%;
        height: 50px;
        font-size: 30px;
        padding: 0 20px;
    }

    .option-value p{
        margin-top: 8px;
    }
</style>