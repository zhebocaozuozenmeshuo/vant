<template>
  <demo-section>
    <demo-block :title="$t('basicUsage')">
      <van-submit-bar
        :price="3050"
        :buttonText="$t('submit')"
        @submit="onClickButton"
      />
    </demo-block>

    <demo-block :title="$t('disabled')">
      <van-submit-bar
        disabled
        :price="3050"
        :buttonText="$t('submit')"
        :tip="$t('tip1')"
        @submit="onClickButton"
      />
    </demo-block>

    <demo-block :title="$t('loading')">
      <van-submit-bar
        loading
        :price="3050"
        :buttonText="$t('submit')"
        @submit="onClickButton"
      />
    </demo-block>

    <demo-block :title="$t('advancedUsage')">
      <van-submit-bar
        :price="3050"
        :buttonText="$t('submit')"
        @submit="onClickButton"
      >
        <van-checkbox v-model="checked">{{ $t('check') }}</van-checkbox>
        <span slot="tip">
          {{ $t('tip2') }}<span class="van-edit-address" @click="onClickLink">{{ $t('tip3') }}</span>
        </span>
      </van-submit-bar>
    </demo-block>
  </demo-section>
</template>

<script>
export default {
  i18n: {
    'zh-CN': {
      submit: '提交订单',
      tip1: '您的收货地址不支持同城送, 我们已为您推荐快递',
      tip2: '您的收货地址不支持同城送, ',
      tip3: '修改地址',
      check: '全选',
      clickButton: '点击按钮',
      clickLink: '修改地址'
    },
    'en-US': {
      submit: 'Submit',
      tip1: 'Some tips',
      tip2: 'Some tips, ',
      tip3: 'Link',
      check: 'Label',
      clickButton: 'Click button',
      clickLink: 'Click Link'
    }
  },

  data() {
    return {
      checked: true
    };
  },

  methods: {
    onClickButton() {
      Toast(this.$t('clickButton'));
    },
    onClickLink() {
      Toast(this.$t('clickLink'));
    }
  }
};
</script>

<style lang="postcss">
.demo-submit-bar {
  .van-submit-bar {
    position: relative;
  }

  .van-edit-address {
    color: #38F;
  }

  .van-checkbox {
    margin-left: 15px;
  }
}
</style>
