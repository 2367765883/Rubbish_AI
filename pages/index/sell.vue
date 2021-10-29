<template>
	<view>
        <category :categoryList="categoryList" :subCategoryList="subCategoryList" @categoryMainClick="categoryMainClick" @categorySubClick="categorySubClick"></category>
    </view>
</template>
    <script>
        import category from "../../components/qiyue-category/qiyue-category.vue"
        export default {
            components:{
                category
            },
            data() {
                return {
                    categoryList:[],
                    subCategoryList:[]
                }
            },
            methods: {
                categoryMainClick(category){
                    this.subCategoryList = category.subCategoryList;
                },
                categorySubClick(category){
                    console.log(category);
                }
            },
            mounted() {
                for(var i=0;i<10;i++){
                    var subList = [];
                    for(var j=0;j<30;j++){
                        subList.push({"name":"分类"+(i+1)+":商品"+(j+1),"logo":"../../static/img/goods.png"})
                    }
                    this.categoryList.push({"name":"分类"+(i+1),"subCategoryList":subList})
                }
                this.subCategoryList = this.categoryList[0].subCategoryList;
            }
        }
    </script>