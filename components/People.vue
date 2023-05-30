<template>
  <div class="bg-white py-24 sm:py-32">
    <div class="mx-auto grid max-w-7xl gap-x-8 gap-y-20 px-6 lg:px-8 xl:grid-cols-3">
      <div class="max-w-2xl">
        <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">我们的团队</h2>
      </div>
      <ul role="list" class="grid gap-x-8 gap-y-12 sm:grid-cols-2 sm:gap-y-16 xl:col-span-2">
        <li v-for="person in people" :key="person.name">
          <div class="flex items-center gap-x-6">
            <img class="h-16 w-16 rounded-full" :src="person.imageUrl" alt="" />
            <div>
              <h3 class="text-base font-semibold leading-7 tracking-tight text-gray-900">{{ person.name }}</h3>
              <p class="text-sm font-semibold leading-6 text-indigo-600">{{ person.role }}</p>
            </div>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      people: [
        {
          name: 'windy Pixel TSX',
          role: '队长',
          imageUrl:
            'https://img.equaapps.net/wpt2199.jpg',
        },
        {
          name: 'Easysys',
          role: '前端开发者',
          imageUrl:
            'https://img.equaapps.net/sys0706.jpg',
        },
        {
          name: '方程式',
          role: '程序开发者',
          imageUrl:
            'https://img.equaapps.net/fcs1024.jpg',
        },
        {
          name: 'XU',
          role: '程序开发者',
          imageUrl:
            'https://img.equaapps.net/xur6688.jpg',
        },
        {
          name: 'ZYH',
          role: '测试',
          imageUrl:
            'https://img.equaapps.net/zyh1127.jpg',
        },
        {
          name: 'Jacky_Liu',
          role: '程序开发者',
          imageUrl:
            'https://img.equaapps.net/jkl1028.jpg',
        },
        {
          name: '虚拟稽',
          role: '程序开发者',
          imageUrl:
            'https://img.equaapps.net/xnj0719.jpg',
        },
      ]
    }
  }
}
</script>


