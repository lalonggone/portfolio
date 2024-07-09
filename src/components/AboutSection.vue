<template>
  <section class="about-section">
    <div class="about-content">
      <h1 class="about-title">about me</h1>
      <p class="about-description">
        I’m Laura, a web developer committed to making a positive impact. I specialize in creating intuitive web
        applications and I believe in the
        power of technology to improve people's lives - if you don't, we're screwed!
      </p>
      <p class="about-description">
        I hold a B.S. in Outdoor Recreation Leadership and Management from Northern Michigan University. My degree and
        experience as a bicycle tour guide has deepened my
        commitment to sustainability and community well-being.
      </p>
      <p class="about-description">
        My journey in activism started in 2016, phone banking for state and national political campaigns. I
        saw firsthand how community engagement and grassroots activism can be a powerful catalyst for change. Lately,
        I've become more involved in local politics, still striving to uphold
        democratic principles.
      </p>
      <p class="about-description">
        When I’m not coding or rallying for a cause, you can try to catch me on my bike, but good luck - I'm proably
        racing the impending doom ;)
      </p>
    </div>
    <div class="about-image">
      <img class="profile-image" src="../assets/selfie.jpg" alt="Laura Long" />
    </div>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'About'
});
</script>

<style lang="scss" scoped>
.about-section {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 50px;
  padding-top: 10vh;
  background-color: var(--bg-color);

  .about-content {
    flex: 1;
    margin-right: 20px;

    .about-title {
      font-size: 2.5rem;
      margin: 40px 0 30px;
    }

    .about-description {
      font-size: 1.1rem;
      line-height: 1.6;
      margin-bottom: 20px;
    }
  }

  .about-image {
    flex: 1;
    text-align: end;

    .profile-image {
      max-width: 80%;
      height: auto;
      border-radius: 10px;
      border: 1px solid var(--text-color);
      margin-top: 5rem;
    }
  }
}
</style>