<template>
    <div> 
      <v-card>
      <v-card-title >
            <div>
                <h1> Firstname:  {{firstName}}</h1>
                <h1> Lastname:  {{lastName}}</h1>   
            </div>
      </v-card-title>
      <v-card-text v-if="id" >
            <div>
              <h1>Id:  {{id}}</h1>   
            </div>
      </v-card-text>
      </v-card>
    </div>
</template>


<script>

const capitalize=(string) =>{
    return string.charAt(0).toUpperCase() + string.slice(1);
}

export default {
  async asyncData ({ params }) {
    const slug = params.slug ;
    const newSlug=slug.split("-"); 
    const firstName = capitalize(newSlug[0]);
    const lastName = capitalize(newSlug[1]) ;
    const id = newSlug[2];
    return { firstName,lastName,id }
  }
}
</script>
