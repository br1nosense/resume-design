<template>
  <div class="person-menu-box">
    <el-menu :default-active="route.name" class="el-menu-vertical-demo">
      <el-menu-item index="PersonDetail" @click="toPersonDetail">
        <svg-icon
          icon-name="icon-jibenziliao"
          class="iconfont"
          :color="getIconColor('PersonDetail')"
          size="22px"
        ></svg-icon>
        <span>个人信息</span>
      </el-menu-item>
      <el-menu-item index="AccountSetting" @click="toAccountSetting">
        <svg-icon
          icon-name="icon-shezhi"
          class="iconfont"
          :color="getIconColor('AccountSetting')"
          size="20px"
        ></svg-icon>
        <span>账号设置</span>
      </el-menu-item>
      <el-menu-item index="MyResume" @click="toMyResume">
        <svg-icon
          icon-name="icon-xiangmujingli-04"
          class="iconfont"
          :color="getIconColor('MyResume')"
          size="20px"
        ></svg-icon>
        <span>我的简历</span>
      </el-menu-item>
      <el-menu-item index="MyOnlineResume" @click="toMyOnlineResume">
        <svg-icon
          icon-name="icon-zaixianyonghu"
          class="iconfont"
          :color="getIconColor('MyOnlineResume')"
          size="20px"
        ></svg-icon>
        <span>在线简历</span>
      </el-menu-item>
      <el-menu-item index="MyContribute" @click="toMyContribute">
        <svg-icon
          icon-name="icon-caogaoxiang1"
          class="iconfont"
          :color="getIconColor('MyContribute')"
          size="20px"
        ></svg-icon>
        <span>我的贡献</span>
      </el-menu-item>
    </el-menu>
  </div>
</template>
<script lang="ts" setup>
  import { MenuItemClicked } from 'element-plus';

  const route = useRoute();
  const router = useRouter();
  // 返回图标颜色
  const currentIndex = ref<any>(route.name); // 选中的菜单index
  const getIconColor = (index: string) => {
    return currentIndex.value === index ? '#2cbd99' : '#303133';
  };

  // 跳转至个人详情
  const toPersonDetail = (item: MenuItemClicked) => {
    currentIndex.value = item.index;
    router.push('/person/personDetail');
  };

  // 跳转至账号设置
  const toAccountSetting = (item: MenuItemClicked) => {
    currentIndex.value = item.index;
    router.push('/person/accountSetting');
  };

  // 跳转至我的简历页面
  const toMyResume = (item: MenuItemClicked) => {
    currentIndex.value = item.index;
    router.push('/person/myResume');
  };

  // 跳转至我的贡献页面
  const toMyContribute = (item: MenuItemClicked) => {
    currentIndex.value = item.index;
    router.push('/person/myContribute');
  };

  // 跳转至我的在线简历
  const toMyOnlineResume = (item: MenuItemClicked) => {
    currentIndex.value = item.index;
    router.push('/person/myOnlineResume');
  };
</script>
<style lang="scss" scoped>
  .person-menu-box {
    padding: 30px 0 10px 0;
    .iconfont {
      margin-right: 15px;
    }
  }
</style>
