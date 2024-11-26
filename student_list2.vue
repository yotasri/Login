<template>
  <v-app>
    <!-- App Bar -->
    <v-app-bar color="teal-darken-2" elevation="2">
      <template v-slot:prepend>
        <div class="rounded-circle d-flex justify-center align-center" style="background-color: white; width: 40px; height: 40px;">
          <v-icon color="teal-darken-2" size="24">mdi-arrow-left</v-icon>
        </div>
      </template>
      <v-app-bar-title>Student List</v-app-bar-title>
      <v-spacer></v-spacer>
      <v-menu>
        <template v-slot:activator="{ props }">
          <v-btn v-bind="props" variant="text">
            Sort by time <v-icon>mdi-chevron-down</v-icon>
          </v-btn>
        </template>
        <v-list>
          <v-list-item value="newest">
            <v-list-item-title>Newest First</v-list-item-title>
          </v-list-item>
          <v-list-item value="oldest">
            <v-list-item-title>Oldest First</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>

    <!-- Main Content -->
    <v-main class="bg-grey-lighten-3">
      <v-container class="px-2">
        <div class="text-subtitle-2 text-grey-darken-1 mb-4">
          E1 เทคโนโลยีสารสนเทศ<br>
          ครูที่ปรึกษา : ครูกฤษณุา แนววิเศษ
        </div>

        <v-list bg-color="#f5f5f5" class="custom-list">
          <v-list-item
            v-for="(item, index) in activities"
            :key="index"
            :class="{'border-b': index !== activities.length - 1}"
            class="activity-item" 
          >
            <template v-slot:prepend>
              <v-avatar size="48" color="info" class="mr-3">
                <v-img :src="'http://localhost:7000/uploads/profile/' + item.picture" max-width="100px" max-height="100px"></v-img>
              </v-avatar>
            </template>

            <v-list-item-title class="font-weight-medium">
              {{ item.username }}
            </v-list-item-title>
            <v-list-item-subtitle class="text-grey-darken-1">
              {{ item.student_id }}
            </v-list-item-subtitle>

            <template v-slot:append>
              <div class="d-flex flex-column align-end">                
                <v-menu location="bottom end">
                  <template v-slot:activator="{ props }">
                    <v-icon 
                      v-bind="props"
                      size="18" 
                      class="cursor-pointer"
                    >
                      mdi-dots-horizontal
                    </v-icon>
                  </template>
                  <v-list>
                    <v-list-item
                      v-for="(option, i) in attendanceOptions"
                      :key="i"
                      @click="updateAttendance(index, option.value)"
                    >
                      <v-list-item-title>{{ option.text }}</v-list-item-title>
                    </v-list-item>
                  </v-list>
                </v-menu>
                <div class="text-grey-darken-1 text-caption mb-1">
                  <span v-if="item.attendance !== undefined" class="ml-2">({{ item.attendance }})</span>
                </div>
              </div>
            </template>
          </v-list-item>
        </v-list>
        <v-btn @click="submitAttendance" color="primary" class="mt-4">
          Submit Attendance
        </v-btn>
      </v-container>
    </v-main>

    <!-- Bottom Navigation -->
    <v-bottom-navigation grow color="teal-darken-2">
      <v-btn value="home">
        <v-icon>mdi-home</v-icon>
        Home
      </v-btn>
      <v-btn value="chat">
        <v-icon>mdi-chat</v-icon>
        Chat
      </v-btn>
      <v-btn value="mail">
        <v-icon>mdi-email</v-icon>
        Mail
      </v-btn>
      <v-btn value="profile">
        <v-icon>mdi-account</v-icon>
        Profile
      </v-btn>
    </v-bottom-navigation>
  </v-app>
</template>

<script setup>
import axios from "axios"
import { ref, onMounted } from 'vue'

const attendanceOptions = [
  { text: 'ขาด', value: 0 },
  { text: 'ลา', value: 0.5 },
  { text: 'มา', value: 1 },
  { text: 'สาย', value: 0.5 }
]

const activities = ref([])

// Function to fetch data from the API
const listData = async () => {
  try {
    const response = await axios.get("http://localhost:7000/listStudent");
    activities.value = response.data.datas;
  } catch (error) {
    console.error('Error fetching data:', error);
  }
}

onMounted(() => {
  listData();
})

const updateAttendance = (index, value) => {
  activities.value[index] = {
    ...activities.value[index],
    attendance: value
  }
}

const submitAttendance = async () => {
  const payload = activities.value.map(activity => ({
    studentName: activity.username,
    studentId: activity.student_id,
    attendance: activity.attendance,
    password: activity.password,
    picture: activity.picture
  }))
  
  try {
    const response = await axios.post("http://localhost:7000/insert1", { activities: payload });
    console.log('API Response:', response.data);
  } catch (error) {
    console.error('Error sending data to API:', error);
  }
}
</script>

<style scoped>
.border-b {
  border-bottom: 1px solid rgba(0, 0, 0, 0.12);
}

.custom-list {
  border-radius: 4px;
  overflow: hidden;
}

.activity-item {
  transition: background-color 0.2s ease;
}

.activity-item:hover {
  background-color: #ffffff !important;
  cursor: pointer;
}
</style>
