<template>
  <div class="pos">
    <el-row id="pos_main">
      <el-col
        :span="7"
        class="pos_order"
        id="posOrder"
      >
        <el-tabs type="border-card">
          <el-tab-pane label="点餐">
            <el-table
              style="width:100%"
              border
              :data="orderData"
            >
              <el-table-column
                prop="goodsName"
                label="商品名称"
              >
              </el-table-column>
              <el-table-column
                prop="count"
                label="数量"
                width="65"
              >
              </el-table-column>
              <el-table-column
                prop="price"
                label="金额"
                width="65"
              >
              </el-table-column>
              <el-table-column
                label="操作"
                width="90"
                fixed="right"
              >
                <template slot-scope="scope">
                  <el-button
                    @click="handleDelete(scope.row)"
                    type="text"
                    size="small"
                  >删除</el-button>
                  <el-button
                    @click="handleAdd(scope.row)"
                    type="text"
                    size="small"
                  >增加</el-button>
                </template>
              </el-table-column>
            </el-table>
            <div class="bottom_btn">
              <el-button
                type="warning"
                size="small"
              >挂单</el-button>
              <el-button
                type="danger"
                size="small"
              >删除</el-button>
              <el-button
                type="success"
                size="small"
              >结账</el-button>
            </div>
          </el-tab-pane>
          <el-tab-pane label="挂单">挂单</el-tab-pane>
          <el-tab-pane label="外卖">外卖</el-tab-pane>
        </el-tabs>
      </el-col>
      <el-col :span="17">
        <div class="often_goods_title">常点商品</div>
        <div class="often_goods_list">
          <ul>
            <li
              v-for="goods in goodsList"
              v-bind:key="goods.id"
            >
              <span>{{goods.name}}</span>
              <span>￥{{goods.price}}元</span>
            </li>
          </ul>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
  export default {
    name: 'Index',
    data() {
      return {
        orderData: [
          {
            goodsName: '鸡腿汉堡',
            count: 1,
            price: 17
          },
          {
            goodsName: '鸡腿汉堡',
            count: 1,
            price: 17
          },
          {
            goodsName: '鸡腿汉堡',
            count: 1,
            price: 17
          },
          {
            goodsName: '鸡腿汉堡',
            count: 1,
            price: 17
          }
        ],
        goodsList: [
          {
            id: 1,
            name: '香辣鸡腿堡',
            price: 18
          },
          {
            id: 1,
            name: '香辣鸡腿堡',
            price: 18
          },
          {
            id: 1,
            name: '香辣鸡腿堡',
            price: 18
          },
          {
            id: 1,
            name: '香辣鸡腿堡',
            price: 18
          },
          {
            id: 1,
            name: '香辣鸡腿堡',
            price: 18
          },
          {
            id: 1,
            name: '香辣鸡腿堡',
            price: 18
          },
          {
            id: 1,
            name: '香辣鸡腿堡',
            price: 18
          },
          {
            id: 1,
            name: '香辣鸡腿堡',
            price: 18
          }
        ]
      }
    },
    mounted() {
      const clientHeight = document.body.clientHeight
      document.getElementById('posOrder').style.height = `${clientHeight}px`
    },
    methods: {
      handleAdd() {},
      handleDelete() {}
    }
  }
</script>

<style scoped>
  .pos_order {
    border-right: 2px solid #e4e7ed;
  }
  .bottom_btn {
    text-align: center;
    margin-top: 10px;
    min-width: 195px;
  }
  .often_goods_title {
    height: 40px;
    border: 1px solid #e4e7ed;
    font-size: 18px;
    font-weight: bold;
    line-height: 39px;
    padding-left: 10px;
  }
  .often_goods_list ul {
    padding: 5px 0px 0px 5px;
  }
  .often_goods_list ul li {
    padding: 8px;
    margin: 5px;
    float: left;
    border: 1px solid #d2d4da;
    border-radius: 5px;
  }
  .often_goods_list ul li span:last-child {
    color: #409eff;
    font-weight: bold;
    font-size: 16px;
    margin-left: 5px;
  }
</style>
