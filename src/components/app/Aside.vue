<template>
  <el-scrollbar>
    <el-menu class="el-menu-vertical-demo">
      <div v-for="item in menuList" :key="item.path">
        <!-- 没有子菜单 -->
        <template v-if="item.children && item.children.length == 0">
          <el-menu-item :index="item.path">
            <i class="el-icon-menu"></i>
            {{ item.title }}
          </el-menu-item>
        </template>

        <!-- 有子菜单 -->
        <el-submenu v-else :index="item.path">
          <template #title>
            <i class="el-icon-menu"></i>
            {{ item.title }}
          </template>

          <template v-for="child in item.children">
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
    </el-menu>
  </el-scrollbar>
</template>
<script lang="ts">
import AsideItem from "./AsideItem.vue";
import { defineComponent } from "vue";
export default defineComponent({
  name: "Aside",
  components: {
    AsideItem,
  },
  setup() {
    const menuList = [
      {
        path: "/awaitdoing", //菜单项所对应的路由路径
        title: "功能1", //菜单项名称
        children: [], //是否有子菜单，若没有，则为[]
      },
      {
        path: "/quickset",
        title: "功能2",
        children: [],
      },
      {
        path: "aa",
        title: "功能3",
        children: [
          {
            path: "/awaitdo",
            title: "功能3-1",
            children: [],
          },
           {
            path: "/awaitdo",
            title: "功能3-1",
            children: [],
          },
           {
            path: "/awaitdo",
            title: "功能3-1",
            children: [],
          },
           {
            path: "/awaitdo",
            title: "功能3-1",
            children: [],
          },
           {
            path: "/awaitdo",
            title: "功能3-1",
            children: [],
          },
           {
            path: "/awaitdo",
            title: "功能3-1",
            children: [],
          },
           {
            path: "/awaitdo",
            title: "功能3-1",
            children: [],
          },
           {
            path: "/awaitdo",
            title: "功能3-1",
            children: [],
          },
           {
            path: "/awaitdo",
            title: "功能3-1",
            children: [],
          },
           {
            path: "/awaitdo",
            title: "功能3-1",
            children: [],
          },
          {
            path: "/alreadygreen",
            title: "功能3-2",
            children: [],
          },
          {
            path: "/approvedby",
            title: "功能3-3",
            children: [],
          },
          {
            path: "bb",
            title: "功能3-4",
            children: [
              {
                path: "/awaitdo2",
                title: "功能3-121",
                children: [
                ],
              },
            ],
          },
        ],
      },
      {
        path: "/func10",
        title: "功能10",
        children: [],
      },
    ];
    return {
      menuList,
    };
  },
});
</script>