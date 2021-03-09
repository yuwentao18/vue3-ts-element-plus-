<template>
  <div>
     <el-submenu >
          <template #title>
            <i class="el-icon-menu"></i>
            {{ menuList.title }}
          </template>

          <template v-for="child in menuList.children">
            <!-- 这里是类似递归循环 -->
            <AsideItem
              v-if="child.children && child.children.length > 0"
              :menuList="child"
              :key="child.path"
            />
            <el-menu-item v-else :key="child.path" :index="child.path">
              <i class="el-icon-location"></i>
              {{ child.title }}
            </el-menu-item>
          </template>
        </el-submenu>
  </div>
</template>
<script>
import { defineComponent, toRefs } from "vue";
export default defineComponent({
  name: "AsideItem",
  props: {
    menuList: Array,
  },
  setup(props) {
    const { menuList } = toRefs(props);
    console.log(menuList);
    return {};
  },
});
</script>