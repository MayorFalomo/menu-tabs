<template>
    <div class="jobsContent" > 
        <ul>
            <li :style="{color: currentPerson == 0 ? '#14B8A6' : '', borderLeft: currentPerson == 0 ? '2px #14B8A6 solid' : '' }" @click="currentPerson = 0 " > TOMMY </li>
            <li :style="{color: currentPerson == 1 ? '#14B8A6' : '', borderLeft: currentPerson == 1 ? '2px #14B8A6 solid' : '' }" @click="currentPerson = 1 " > BIGDROP </li>
            <li :style="{color: currentPerson == 2 ? '#14B8A6' : '', borderLeft: currentPerson == 2 ? '2px #14B8A6 solid' : '' }" @click="currentPerson = 2 " > CUKER </li>
        </ul>

        <div>
          <div class="contentContainer" >
        <h1>{{contents[currentPerson].position }} </h1>
        <span> {{contents[currentPerson].name }} </span>
        <p> {{contents[currentPerson].Date }} </p>
    </div>

    <div class="flexTexts" >
        <p><span><Icon icon="uit:angle-double-right" /> </span> {{contents[currentPerson].firstComment}} </p>
        <p><span><Icon icon="uit:angle-double-right" /> </span> {{contents[currentPerson].secondComment}} </p>
        <p><span><Icon icon="uit:angle-double-right" /> </span> {{contents[currentPerson].thirdComment}} </p>
    </div>
    </div>
    </div>
</template>

<script>
import Content from "./Content.vue";
import { Icon } from '@iconify/vue';

export default {
    name: "Jobs",
    components: {
        Content,
        Icon
    },
    data() {
        return {
            contents: [
        {
            id: 1,
            position: "Full Stack Web Developer",
            name: "TOMMY",
            Date: "December 2015 - Present",
            firstComment: "Tote bag sartorial mlkshk air plant vinyl banjo lumbersexual poke leggings offal cold-pressed brunch neutra. Hammock photo booth live-edge disrupt.",
            secondComment: "Post-ironic selvage chambray sartorial freegan meditation. Chambray chartreuse kombucha meditation, man bun four dollar toast street art cloud bread live-edge heirloom.",
          thirdComment: "Butcher drinking vinegar franzen authentic messenger bag copper mug food truck taxidermy. Mumblecore lomo echo park readymade iPhone migas single-origin coffee franzen cloud bread tilde vegan flexitarian.",
            category: "Web-Dev",
        },
        {
            id: 2,
            position: "Front-End Engineer",
            name: "BIGDROP",
            Date: "May 2015 - December 2015",
            firstComment: "Hashtag drinking vinegar scenester mumblecore snackwave four dollar toast, lumbersexual XOXO. Cardigan church-key pabst, biodiesel vexillologist viral squid.",
            secondComment: "Franzen af pitchfork, mumblecore try-hard kogi XOXO roof party la croix cardigan neutra retro tattooed copper mug. Meditation lomo biodiesel scenester",
            thirdComment: "Fam VHS enamel pin try-hard echo park raw denim unicorn fanny pack vape authentic. Helvetica fixie church-key, small batch jianbing messenger bag scenester +1",
          fourthComment:  " Fam VHS enamel pin try-hard echo park raw denim unicorn fanny pack vape authentic. Helvetica fixie church-key, small batch jianbing messenger bag scenester +1"
        },
        {
            id: 3,
            position: "Engineering Intern",
            name: "CUKER",
            Date: "May 2014 - September 2015",
            firstComment: "I'm baby woke mumblecore stumptown enamel pin. Snackwave prism pork belly, blog vape four loko sriracha messenger bag jean shorts DIY bushwick VHS. Banjo post-ironic hella af, palo santo craft beer gluten-free.",
            secondComment: "YOLO drinking vinegar chambray pok pok selfies quinoa kinfolk pitchfork street art la croix unicorn DIY. Woke offal jianbing venmo tote bag, palo santo subway tile slow-carb post-ironic pug ugh taxidermy squid.",
          thirdComment: "Pour-over glossier chambray umami 3 wolf moon. Iceland kale chips asymmetrical craft beer actually forage, biodiesel tattooed fingerstache. Pork belly lomo man braid, portland pitchfork locavore man bun prism.",
            category: "intern",
        },
    ],
    currentPerson: 0,
    activeNumber: 0,
        }    
    },
    methods: {

    }
}
</script>

<style>
.jobsContent{
    display: flex;
    align-items: flex-start;
    gap: 50px;
    width: 80%;
    margin:0 auto;
        margin-top: 50px ;
        margin-bottom: 30px;
}
.jobsContent ul{
    display: flex;
    flex-direction: column;
    gap: 15px;
}
.jobsContent ul li{
    padding: 5px 10px;
    cursor: pointer;
    font-size: 20px;
    width: 150px;
    max-width: 200px;
    text-align: center;
    list-style: none;
}

.contentContainer {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 20px;
}
.contentContainer span{
    background-color: #CBD5E1;
    padding: 10px 15px;
    border-radius: 8px;
    font-size: 20px;
    opacity: 0.8;
  
}
.contentContainer P{
    font-size: 20px;
}
.flexTexts {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 30px;
    width: 90%;
    margin-top: 25px;
}
.flexTexts span{
    font-size: 30px;
    font-weight: 600;
    color: #14B8A6;
}
.flexTexts p{
    /* border: 2px red solid; */
    display: flex;
    align-items: center;
    gap: 15px;
    font-size: 20px;
    line-height: 30px;
}
@media (max-width: 800px ) {
    .jobsContent{
        width: 95%;
    }
}
@media (max-width: 650px ) {
    .jobsContent{
      flex-direction: column;
    }
    .jobsContent ul{
      width: 100%;
      
    }
    .flexTexts {
        width: 95%;
    }
    .flexTexts p{
        gap: 5px;
    }
}
</style>