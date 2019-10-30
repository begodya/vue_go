/* eslint-disable semi */
/* ------------------------------------------- template ------------------------------------------- */
<template>
  <div>
    <div>{{sWord}}</div>
    <div>1. 什么是 Typescript?</div>
    <div>2. Typescript 的优缺点</div>
    <div>3. Typescript 基础</div>
  </div>
</template>

/* -------------------------------------------- script -------------------------------------------- */
<script lang="ts">
import { Component, Prop, Vue, Watch } from 'vue-property-decorator';

@Component
export default class Demo extends Vue {
  sWord: string = 'Hello Typescript!'; // sWord 内部属性

  /* ----------------------1. 生命周期函数------------------------ */
  created () {
    this.showMeCode();
  }

  /* ----------------------2. 监听属性函数------------------------ */
  // 监听 sWord 是否发生改变
  @Watch('sWord')
  onChangeValue (newV: string, oldV: string) {
    if (newV !== oldV) {
      alert('监控状态已经发生改变！！！');
    } else {
      alert('监控状态尚未发生改变！！！');
    }
  }

  mounted (): void {
    setTimeout(() => {
      this.sWord = 'Typescript Demo页面';
    }, 1500);
  }

  /* ----------------------3. 事件调用函数------------------------ */

  /* ----------------------4. 内部功能函数------------------------ */
  showMeCode (): void {
    // 原始数据类型
    this.showDataTypeCode();

    // 任意值
    this.showAnyTypeCode();

    // 类型推论
    this.showTypeInferenceCode();

    // 联合类型
    this.showUnionTypesCode();

    // 对象类型接口
    this.showInterfaceCode();
  }

  // 原始数据类型
  showDataTypeCode (): void {
    // boolean
    let isDone: boolean = false;
    // let createdByNewBoolean1: Boolean = new Boolean(1);
    // console.log('createdByNewBoolean1 =' + createdByNewBoolean1);
    let createdByNewBoolean2: Boolean = Boolean(1);
    console.log('createdByNewBoolean2 =' + createdByNewBoolean2);
    let createdByNewBoolean3: boolean = Boolean(1);
    console.log('createdByNewBoolean3 =' + createdByNewBoolean3);

    // 数值
    let nDecLiteral: number = 7;
    let nhexLiteral: number = 0xf00d;
    let nbinaryLiteral: number = 0b1010;
    let nOctalLiteral: number = 0o744;
    let nNotANumber: number = NaN;
    let nInfinityNumber: number = Infinity;

    // 字符串
    let sName: string = 'begodya';
    let nAge: number = 17;
    let sSentence: string = `Hello, my name is ${sName}. I'll be ${nAge +
      1} years old next month.`;
    console.log(sSentence);

    // 空值、Null、Undefined
    let unusale: void;
    let u: undefined;
    let n: null = null;
  }

  // 任意值
  showAnyTypeCode (): void {
    let myFavoriteNumber: any = 'seven';
    console.log(`myFavoriteNumber = ${myFavoriteNumber}`);
    myFavoriteNumber = 7;
    console.log(`myFavoriteNumber = ${myFavoriteNumber}`);
  }

  // 类型推论
  showTypeInferenceCode (): void {
    // let myFavoriteNumber = 'SEVEN';
    // myFavoriteNumber = 7;

    let myFavoriteNumber;
    myFavoriteNumber = 'seven';
    myFavoriteNumber = 7;
  }

  // 联合类型
  showUnionTypesCode (): void {
    let myFavoriteNumber: string | number;
    myFavoriteNumber = 'seven';
    myFavoriteNumber = 7;
    // myFavoriteNumber = true;
  }

  // 对象类型接口
  showInterfaceCode (): void {
    interface Person {
      name: string;
      age: number;
      gender?: string;
    }

    let tom: Person = {
      name: 'Tom',
      age: 18
    };
  }

  // 数组类型
  showArrayCode (): void {
    let aFoo: number[] = [1, 2, 3, 4, 5, 6];
    // let aFoo: number[] = [1, 2, 3, 4, 5, '6'];
    console.log('aFoo = ' + aFoo);

    let aGoo: Array<number> = [7, 8, 9, 10, 11];
    console.log('aGoo = ' + aGoo);
  }

  /* ----------------------5. 服务请求函数------------------------ */
}
</script>

/* -------------------------------------------- style -------------------------------------------- */
<style scoped lang="scss">
</style>
