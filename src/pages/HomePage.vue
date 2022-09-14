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

        <div class="col-md-9 position-relative">
          <Transition>

            <ProjectMagic v-if="project == 'magic'" />
          </Transition>
          <Transition>

            <ProjectTower v-if="project == 'tower'" />
          </Transition>
          <Transition>

            <ProjectNetwork v-if="project == 'network'" />
          </Transition>
          <Transition>

            <ProjectInspire v-if="project == 'inspire'" />
          </Transition>
          <Transition>

            <ProjectWayfinder v-if="project == 'wayfinder'" />
          </Transition>
          <Transition>

            <ProjectMoonMiner v-if="project == 'moon'" />
          </Transition>

          <Transition>
            <ProjectSiteClone v-if="project == 'clone'" />
          </Transition>
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
import ProjectMagic from "../components/ProjectMagic.vue";
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
  components: { ProjectSiteClone, ProjectMoonMiner, ProjectWayfinder, ProjectInspire, ProjectNetwork, ProjectTower, ProjectMagic }
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

.v-enter-active,
.v-leave-active {
  transition: opacity .75s ease-in-out;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>