<template>
  <div class="home">
    <div v-if="role === $GLOBAL.role.user">
      <InfoNoteUser />
      <WelcomeUser class="mt-8" />
      <LatestOrder class="mt-8" />
    </div>
    <div v-else-if="role === $GLOBAL.role.solver">
      <WelcomeSolver />
      <AcceptedOrder class="mt-8" />
    </div>
  </div>
</template>

<script>
import InfoNoteUser from '@/components/Home/InfoNoteUser'
import WelcomeUser from '@/components/Home/WelcomeUser'
import LatestOrder from '@/components/Order/LatestOrder'
import WelcomeSolver from '@/components/Home/WelcomeSolver.vue'
import AcceptedOrder from '@/components/Order/AcceptedOrder'

export default {
  data: () => ({
    role: null
  }),
  name: 'Home',
  components: {
    InfoNoteUser,
    WelcomeUser,
    LatestOrder,
    WelcomeSolver,
    AcceptedOrder
  },
  created () {
    this.role = this.$store.state.role
  }
}
</script>
