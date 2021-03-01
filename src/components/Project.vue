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
              <v-btn v-if="project.link" text :class="`${project.color} mr-2`" dark @click="github(project.link)"><v-icon>mdi-github</v-icon> View Code</v-btn>
              <v-btn v-if="project.link1" text :class="`${project.color} mr-2`" dark @click="github(project.link1)"><v-icon>mdi-github</v-icon> Frontend</v-btn>
              <v-btn v-if="project.link2" text :class="`${project.color} mr-2`" dark @click="github(project.link2)"><v-icon>mdi-github</v-icon>  Backend</v-btn>
              <v-btn v-if="project.link3" text :class="`${project.color} mr-2`" dark @click="github(project.link3)"><v-icon>mdi-web</v-icon>  Demo</v-btn>
              <v-btn v-if="project.youtube" text class="primary my-4" dark @click="github(project.youtube)"><v-icon>mdi-youtube</v-icon> Video</v-btn>
            </div>

            <v-row>
              <div v-for="(item, index) in project.items" :key="index">
                <v-col cols="1">
                  <v-tooltip bottom :color="`${item[1]}`">
                    <template v-slot:activator="{ on, attrs }">
                      <v-avatar size="40" v-bind="attrs" v-on="on">
                        <v-icon :color="`${item[1]}`">{{ item[0] }}</v-icon>
                      </v-avatar>
                    </template>
                    <span>{{ item[2] }}</span>
                  </v-tooltip>
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
    dialog: false,
    projects: [
      {
        color: 'teal',
        technology: 'Vue',
        title: 'Field Engineer Management System',
        description: 'This helps companies deliver effective onsite service\n' +
            'by tracking request, managing personnel, and\n' +
            'maintaining visibility into operations',
        // link: 'https://github.com/DSGunasekara/vue-field-engineer',
        link1: 'https://github.com/DSGunasekara/field-engineer-frontend',
        link2: 'https://github.com/DSGunasekara/field-engineer-backend',
        link3: 'https://field-engineer-frontend.herokuapp.com/#/landing',
        items: [['mdi-vuejs', 'teal', 'Vuejs'], ['mdi-nodejs', 'green', 'Nodejs'], ['mdi-language-javascript', '#FFB300', 'JavaScript'], ['mdi-database', 'green', 'MongoDB']]
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
        link: 'https://github.com/DSGunasekara/HRIS-ITP',
          items: [['mdi-angular', '#E53935', 'Angular 9'], ['mdi-nodejs', 'green', 'Nodejs'], ['mdi-language-typescript', 'primary', 'TypeScript'], ['mdi-database', 'green', 'MongoDB']],
        youtube: 'https://www.youtube.com/embed/S3vq-il9fIk'
      },
      {
        color: 'green',
        technology: 'Android',
        title: 'Smoothie Android App',
        description: 'Online Juice ordering platform created with\n' +
            'android and firebase',
        link: 'https://github.com/DSGunasekara/Smoothie',
        items: [['mdi-android', 'green', 'Android'], ['mdi-language-java', '#E53935', 'Java'], ['mdi-firebase', '#FFB300', 'Firebase']],
        youtube: 'https://www.youtube.com/embed/WDYIQAU1gps'
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
        link: '',
        items: [['mdi-raspberry-pi', 'deep-purple', 'Raspberry Pi'], ['mdi-language-python', 'blue-grey', 'Python with Tensorflow']]
      },
      {
        color: 'blue-grey',
        technology: 'Django',
        title: 'A Blog site',
        description: 'A blog website created with using django and postgresql database',
        link: 'https://github.com/DSGunasekara/django-wanderer',
        items: [['mdi-language-python', 'blue-grey', 'Python'], ['mdi-database', 'primary', 'PostgreSQL']],
        youtube: 'https://www.youtube.com/embed/nvxf9SoiNzQ'
      },
    ],
  }),
  methods:{
    github(link){
      if(link) window.open(link)
    },
  }
}
</script>

<style scoped>
@media only screen and (max-width: 600px){
  embed{
    width: auto;
    height: auto;
  }
}

</style>
