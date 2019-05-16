<template>
  <v-container fluid grid-list-md>
    <v-layout row justify-center wrap>
      <UserProfile
        :name="user.name"
        :description="user.description"
        :image-url="user.imageUrl"
      >
      </UserProfile>
      <Popularity />
    </v-layout>
  </v-container>
</template>

<script>
import UserProfile from '@/components/CardUserProfile'
import Popularity from '@/components/CardPopularity'

export default {
  components: {
    UserProfile,
    Popularity
  },
  data: () => ({
    user: {
      imageUrl:
        'https://avataaars.io/?avatarStyle=Circle&topType=ShortHairShortCurly&accessoriesType=Blank&hairColor=BrownDark&facialHairType=Blank&clotheType=BlazerSweater&eyeType=Squint&eyebrowType=RaisedExcitedNatural&mouthType=Default&skinColor=Tanned',
      name: 'Funny Wow',
      description: 'There is a fly on your face'
    }
  })
}
</script>
<style></style>
