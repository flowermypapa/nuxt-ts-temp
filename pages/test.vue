<template>
  <div>{{ message }}</div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'nuxt-property-decorator'

interface User {
  firstName: string
  lastName: number
}

@Component
export default class YourComponent extends Vue {
  @Prop({ type: Object }) readonly user!: User

  private message: string = 'This is a message'

  get fullName(): string {
    return `${this.user.firstName} ${this.user.lastName}`
  }
}
</script>
