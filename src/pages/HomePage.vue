<template>
  <div class="row">
    <!-- SECTION about me -->
    <div class="col-md-3">
      <div class="glass-card position-relative">
        <img class="img-fluid rounded"
          src="https://activerain-store.s3.amazonaws.com/image_store/uploads/9/8/3/5/3/ar13258249335389.jpg" alt="">
        <div class="text-center">
          <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#bioModal">
            About me
          </button>
        </div>
        <p class="mb-0 ">
          Hi, I'm Andrew and I enjoy creating beautiful and performant products with smooth user
          experiences.
        </p>
        <span class="d-flex flex-row fixed-bottom justify-content-around fs-3">
          <a href="https://github.com/AndrewLaRue" title="GitHub">
            <i class="mdi mdi-github"></i>
          </a>
          <a href="https://www.linkedin.com/in/andrew-larue/" title="LinkedIn">
            <i class="mdi mdi-linkedin"></i>
          </a>
          <a href="mailto:a.larue.dev@gmail.com" title="Email">
            <i class="mdi mdi-email"></i>
          </a>
          <a href="https://resume.io/r/kADzK0ox1" title="Resume">
            <i class="mdi mdi-format-float-left"></i>
          </a>
        </span>
      </div>
    </div>

    <!-- SECTION Projects -->
    <section class="col-md-9">
      <div class="row glass-card">
        <div class="col-md-3">
          <h3 class="text-center">Projects</h3>
          <ul class="list-unstyled no-select fs-5">

            <li v-if="project == 'final'" @click="toggle('final')" class="selectable mt-3 active-project text-center">
              <strong>Final</strong>
            </li>
            <li v-else @click="toggle('final')" class="selectable mt-3">
              <strong>Final</strong>
            </li>
            <!-- <p></p> -->

            <li v-if="project == 'magic'" @click="toggle('magic')" class="selectable mt-3 active-project text-center">
              <strong>Magic Medley</strong>
            </li>
            <li v-else @click="toggle('magic')" class="selectable mt-3">
              <strong>Magic Medley</strong>
            </li>
            <!-- <p>
            App Requirements
            ○ Full-Stack Application
            ○ Auth and Access Control
            ○ Professional (No: Drugs, Sex, Politics, Violence, *Games)
            ○ Utilizes new technologies/API's not previously learned
            ○ Readme/About Page of app problem statement, concept, description, contributors, and languages/tools used
            ○ App Documentation for data models, accurate UML and map of endpoints for API
            ○ Deployed live
            Team Requirements
            ○ 3-5 Students
            ○ Assigned Scrum master and Product Owner (different people)
            ○ Must incorporate scrum practices (daily standup, retrospective, sprint review)
            ○ Partner Coding, Break agreements
            Pitch Requirements
            ○ Problem Statement, Concepts, Target Audience, Why
            ○ Research completed for data sources (API, Technology, Content, Cost)
            ○ UML
            ○ Mid-Fidelity FIGMA (Prototype)
            ○ 3 Phase plan for (MVP, IDEAL, FEATURE RICH)
            § Kanban (Trello)
            § Story Map
            App Ideal Features
            ○ Adheres to UI Requirements
            ○ Desktop and Mobile
            ○ Tests (Postman / Unit)
            ○ Vue Tour (or other user onboarding/demo)
            ○ Documented Code (JsDocs)
            ○ Where applicable:
            § Socket Integration
            § File Uploading
            § User Roles
          </p> -->


            <li v-if="project == 'tower'" @click="toggle('tower')" class="selectable mt-3 active-project text-center">
              <strong>Tower</strong>
            </li>
            <li v-else @click="toggle('tower')" class="selectable mt-3">
              <strong>Tower</strong>
            </li>

            <li v-if="project == 'network'" @click="toggle('network')"
              class="selectable mt-3 active-project text-center">
              <strong>The Network</strong>
            </li>
            <li v-else @click="toggle('network')" class="selectable mt-3">
              <strong>The Network</strong>
            </li>

            <li v-if="project == 'inspire'" @click="toggle('inspire')"
              class="selectable mt-3 active-project text-center"><strong>Inspire</strong>
            </li>
            <li v-else @click="toggle('inspire')" class="selectable mt-3">
              <strong>Inspire</strong>
            </li>

            <li v-if="project == 'wayfinder'" @click="toggle('wayfinder')"
              class="selectable mt-3  active-project text-center">
              <strong>Wayfinder</strong>
            </li>
            <li v-else @click="toggle('wayfinder')" class="selectable mt-3"><strong>Wayfinder</strong></li>

            <li v-if="project == 'moon'" @click="toggle('moon')" class="selectable mt-3  active-project text-center">
              <strong>MoonMiner</strong>
            </li>
            <li v-else @click="toggle('moon')" class="selectable mt-3"><strong>MoonMiner</strong></li>

            <li v-if="project == 'clone'" @click="toggle('clone')" class="selectable mt-3  active-project text-center">
              <strong>SiteClone</strong><br>
            </li>
            <li v-else @click="toggle('clone')" class="selectable mt-3"><strong>SiteClone</strong><br></li>
          </ul>
        </div>

        <div class="col-md-9">
          <ProjectTower v-if="project == 'tower'" />
          <ProjectNetwork v-if="project == 'network'" />
          <ProjectInspire v-if="project == 'inspire'" />
          <ProjectWayfinder v-if="project == 'wayfinder'" />
          <ProjectMoonMiner v-if="project == 'moon'" />
          <ProjectSiteClone v-if="project == 'clone'" />
        </div>





      </div>
    </section>
  </div>

  <!-- SECTION about me modal -->
  <div class="modal fade" id="bioModal" tabindex="-1" aria-labelledby="bioModalLabel" aria-hidden="true">
    <div class="modal-dialog modal-dialog-centered text-dark">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="bioModalLabel">Welcome to my Life</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body">
          ...
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import ProjectSiteClone from "../components/ProjectSiteClone.vue";
import ProjectMoonMiner from "../components/ProjectMoonMiner.vue";
import ProjectWayfinder from "../components/ProjectWayfinder.vue";
import ProjectInspire from "../components/ProjectInspire.vue";
import { computed } from "vue";
import { AppState } from '../AppState'
import ProjectNetwork from '../components/ProjectNetwork.vue'
import ProjectTower from '../components/ProjectTower.vue'
export default {
  setup() {
    return {
      project: computed(() => AppState.activeProject),

      toggle(option) {
        AppState.activeProject = ''
        setTimeout(AppState.activeProject = option, 1000)

      }

    };
  },
  components: { ProjectSiteClone, ProjectMoonMiner, ProjectWayfinder, ProjectInspire, ProjectNetwork, ProjectTower }
}
</script>


<style lang="scss" scoped>
.active-project {
  border-left: 10px solid rgb(0, 0, 154);
  border-right: 10px solid rgb(0, 0, 154);
  border-radius: 50%;
}

.glass-card {
  background: rgb(54 52 75 / 38%);
  backdrop-filter: blur(4px);
  border: solid #8d8b8b1f;
  border-radius: 8px;
  padding: 1em;
  color: #f2e9e4;
  text-shadow: 1px 1px 3px black;
  height: 33em;
  margin-top: 3vh;
}

// *::-webkit-scrollbar {
//   display: none;
// }

button {
  font-family: 'Oswald', sans-serif;
  transform: translateY(-20px);
}

.v-enter-active {
  transition: opacity .75s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>