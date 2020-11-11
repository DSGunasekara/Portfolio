<template>
  <div class="container">
    <template>
      <h1 style="text-align: center; color: #00BD9D; font-weight: 400">Project List</h1>
      <v-timeline>
        <v-timeline-item
            v-for="(project, i) in projects"
            :key="i"
            :color="project.color"
            small
        >
          <template v-slot:opposite>
        <span
            :class="`headline font-weight-bold ${project.color}--text`"
            v-text="project.technology"></span>
          </template>
          <div class="py-4">
            <h2 :class="`headline font-weight-light mb-4 ${project.color}--text`">
              {{ project.title}}
            </h2>
            <div>
              {{ project.description}}
            </div>
            <div class="py-4">
              <v-btn text :class="`${project.color}`" dark @click="github(project.link)"><v-icon>mdi-github</v-icon> View Code</v-btn>
            </div>

            <v-row>
              <div v-for="(item, index) in project.items" :key="index">
                <v-col cols="1">
                  <v-avatar size="40">
                    <v-icon :color="`${item[1]}`">{{ item[0] }}</v-icon>
                  </v-avatar>
                </v-col>
              </div>
            </v-row>

          </div>
        </v-timeline-item>
      </v-timeline>
    </template>
  </div>
</template>

<script>
export default {
name: "Project",
  data: () => ({
    projects: [
      {
        color: 'teal',
        technology: 'Vue',
        title: 'Filed Engineer Management System',
        description: 'This helps companies deliver effective onsite service\n' +
            'by tracking request, managing personnel, and\n' +
            'maintaining visibility into operations',
        link: 'https://github.com/DSGunasekara/vue-field-engineer',
        items: [['mdi-vuejs', 'teal'], ['mdi-language-javascript', '#FFB300']]
      },
      {
        color: 'indigo',
        technology: 'Angular',
        title: 'Human Resource Information System',
        description: 'This system is capable of managing employee\n' +
            'data, handling payroll, managing ongoing project\n' +
            'information, managing vehicle fleet, commencing\n' +
            'new training program, publishing announcements\n' +
            'and managing equipment details of the company.\n' +
            'This was created using MEAN stack.',
        link: 'https://github.com/thushaltk/HRIS-ITP',
          items: [['mdi-angular', '#E53935'], ['mdi-nodejs', 'green'], ['mdi-language-typescript', 'primary']]
      },
      {
        color: 'green',
        technology: 'Android',
        title: 'Smoothie Android App',
        description: 'Online Juice ordering platform created with\n' +
            'android and firebase',
        link: 'https://github.com/thushanK/Smoothie',
        items: [['mdi-android', 'green'], ['mdi-language-java', '#E53935'], ['mdi-firebase', '#FFB300']]
      },
      {
        color: 'primary',
        technology: 'Raspberry Pi',
        title: 'IOT based System for Detection and Monitoring\n' +
            'of Microplastic',
        description: 'A device that can detect microplastic in water\n' +
            'bodies and calculate the density of the\n' +
            'microplastic available in that waterbody using a\n' +
            'Raspberry Pi and Machine learning',
        items: [['mdi-raspberry-pi', 'deep-purple'], ['mdi-language-python', '#29B6F6']]
      },
    ],
  }),
  methods:{
    github(link){
      // window.location.href = `https://${link}`
      // this.$router.navigate(link)
      if(link) window.open(link)

    }
  }
}
</script>

<style scoped>

</style>