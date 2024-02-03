<script>
import MenuVue from './components/Menu.vue'
import Jobs from "./components/Jobs.vue"


export default {
  components: {
    MenuVue,
    Jobs,
  },
  data() {
    return {
      //First we initialize selected as a value so the computed properties knows to update when selected changes, Selected is a reactive element and the computed properties will be updated when selected changes,\
      //N.B: Make sure the selected property does not have even a white space else the computed properties might not register it 
          selected: "All",
      menus: [
        {
          id: "1",
            img: "https://react-projects-5-menu.netlify.app/images/item-1.jpeg",
            foodName: "ButterMilk Pancakes",
            price: "$15.99",
            description: "I'm baby woke mlkshk wolf bitters live-edge blue bottle, hammock freegan copper mug whatever cold-pressed",
            category: "Breakfast"
        },
        {
                    id: "2",
             img: "https://react-projects-5-menu.netlify.app/images/item-2.jpeg",
            foodName: "Diner Double",
            price: "$15.99",
            description: "vaporware iPhone mumblecore selvage raw denim slow-carb leggings gochujang helvetica man braid jianbing. Marfa thundercats",
            category: "Breakfast"
        },
        {
                    id: "3",
             img: "https://react-projects-5-menu.netlify.app/images/item-3.jpeg",
            foodName: "Godzilla Milkshake",
            price: "$6.99",
            description: "ombucha chillwave fanny pack 3 wolf moon street art photo booth before they sold out organic viral.",
            category: "Shakes"
        },
        {
                    id: "4",
             img: "https://react-projects-5-menu.netlify.app/images/item-4.jpeg",
            foodName: "Country Delight",
            price: "$20.99",
            description: "Shabby chic keffiyeh neutra snackwave pork belly shoreditch. Prism austin mlkshk truffaut,",
            category: "Breakfast"
        },        
        {
                    id: "5",
             img: "https://react-projects-5-menu.netlify.app/images/item-5.jpeg",
            foodName: "Egg Attack",
            price: "$20.99",
            description: "franzen vegan pabst bicycle rights kickstarter pinterest meditation farm-to-table 90's pop-up",
            category: "Lunch"
        },        
        {
            id: "6",
            img: "https://react-projects-5-menu.netlify.app/images/item-6.jpeg",
            foodName: "Oreo Dream",
            price: "$18.99",
            description: "Portland chicharrones ethical edison bulb, palo santo craft beer chia heirloom iPhone everyday",
            category: "Shakes"
        },        
        {
            id: "7",
            img: "https://react-projects-5-menu.netlify.app/images/item-7.jpeg",
            foodName: "Bacon Overflow",
            price: "$8.99",
            description: "carry jianbing normcore freegan. Viral single-origin coffee live-edge, pork belly cloud bread iceland put a bird",
            category: "Breakfast"
        },        
        {
            id: "8",
            img: "https://react-projects-5-menu.netlify.app/images/item-8.jpeg",
            foodName: "American Classic",
            price: "$12.99",
            description: "on it tumblr kickstarter thundercats migas everyday carry squid palo santo leggings. Food truck truffaut",
            category: "Lunch"
        },        
        {
            id: "10",
            img: "https://react-projects-5-menu.netlify.app/images/item-9.jpeg",
            foodName: "Quarantine Buddy",
            price: "$16.99",
            description: "skateboard fam synth authentic semiotics. Live-edge lyft af, edison bulb yuccie crucifix microdosing.",
            category: "Shakes"
        },        
    ],
    }

  },
  methods: {
    //The filter Category takes in a parameter and that parameter we set the value to be selected
    filterCategory(category){
      this.selected = category;   
      console.log(category, "category");
  },  
  },
  //Now the computed property runs as a useEffect in a way, It's always running like a useEffect and would only rerun when a dependency changes, We return the original array if selected is All but then return a filtered array when selected is not all anymore 
  //Because the computed properties is the one that decides what to show, you have to map over the computed properties itself and not the original array
  computed: {
    filterMenu(){
  if(this.selected == 'All'){
  //  console.log(this.menus, "this menus");
 return this.menus
 } else{
   return this.menus.filter((menuItem) => menuItem.category === this.selected);
    
 }
  }
  },
 
}
</script>

<template>
 <div class="wrapper">
  <h1> Our Menu </h1>
  <div class='underLine' > </div>
  <ul>
    <li @click="filterCategory('All')  " > All </li>
    <li  @click="filterCategory('Breakfast')" > Breakfast </li>
    <li  @click=" filterCategory('Lunch')" > Lunch </li>
    <li  @click=" filterCategory('Shakes')" > Shakes </li>
  </ul>
  <div class="mapped" >
    <div v-for="menuItem in filterMenu" :key="menuItem.id">
      <div class="mappedCon" > 
        <MenuVue :menuItem="menuItem" />
      </div>
    </div>
  </div>
    <div class="switchCon" >
<Jobs  />
  </div>
  </div>

</template>

<style scoped >
.wrapper{
  background-color: #F8FAFC;
  width: 100vw;
  min-height: 100vw;
}
.wrapper h1{
  text-align: center;
  margin-top:30px ;
}
.underLine{
  width: 200px;
  height: 5px;
  display: flex;
  justify-content: center;
  margin:  auto;
  margin-top: 20px;
  margin-bottom: 30px;
  background-color: #F59E0B;
}
.wrapper ul{
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
}
.wrapper ul li{
  list-style: none;
  padding: 7px 15px;
  border-radius: 8px;
  font-size: 18px;
  font-weight: 500;
  background-color: #F59E0B;
  color: #fff;
  cursor: pointer;
  box-shadow: rgba(50, 50, 93, 0.25) 0px 2px 5px -1px, rgba(0, 0, 0, 0.3) 0px 1px 3px -1px;

}
.mapped{
  display: flex;
  align-items: flex-start;
  justify-content: center;
  flex-wrap: wrap;
  gap: 30px;
  max-width: 70%;
  margin: 0 auto;
  margin-top: 30px;
}
.wrapper .mappedCon{
  /* border: 2px blue solid; */
   width: 100%;
    height: fit-content;
    max-width: 500px;
     background-color: white;
}
.switchCon{
    width: 100vw;
    min-height: 100vh;
}
@media (max-width:1465px ) {
  .mapped{
    max-width: 100%;
  }
}
</style>
