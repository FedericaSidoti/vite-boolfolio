<template>
    <div>
        <div class="container">
                <template class="jumbo-wrap">
                </template>
            <div class="card">
                <h2>Hi there! 🖖</h2> 
                        <p>I am <span>Federica Sidoti</span>, a junior full stack web developer and tech enthusiast. </p>
                        <p>I started coding for fun, fixing and making adjustments to <span>RPG websites</span> (WoD never dies, PlayByChat never dies!). </p>
                        <p>Then I rediscovered my passion: one IT course at university and I was in love again!</p>
                        <p>I love learning new coding skills, languages & frameworks: <span>curiosity</span> does NOT kill cats, really (or so I hope). </p>
                        <p>I especially love coding in a team. Since the beginning I learned with great help from teachers, more experienced developers, even forums and friendly neighbourhood enthusiasts on the Web. I feel that <span>working together</span> and <span>never gatekeeping knowledge</span> is one of the best parts in the DEV world. </p>
                        <p>Yes, I'm <span>nerd and a proud one</span>. LARPs and RPGs are my favourite pastimes! (but chess is also worth a mention). </p>
            </div>
        </div>
    </div>
</template>
  
<script>
    export default {
    data() {
        return {
            title: 'Federica Sidoti',
            jobTitle: 'Jr FullStack Developer'
            }
        },
    }
</script>
  
<style lang="scss" scoped>
    .jumbo-wrap{
        display:flex; 
        height: 300px;
        background-image: url(/img/jumbo.gif);
        background-size: contain;
        background-repeat: no-repeat;
        background-position: center;
        background-color: #1F3B4E;
        margin-bottom: 20px; 
        margin-top: 20px;
    }
  
</style>