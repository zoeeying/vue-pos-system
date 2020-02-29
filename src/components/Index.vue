<template>
  <div class="pos">
    <el-row id="posMain">
      <el-col :span="7" class="pos_order" id="posOrder">
        <el-tabs type="border-card">
          <el-tab-pane label="点餐">
            <el-table style="width:100%" border :data="tableData">
              <el-table-column prop="name" label="商品名称"> </el-table-column>
              <el-table-column prop="count" label="数量" width="65">
              </el-table-column>
              <el-table-column prop="price" label="金额" width="65">
              </el-table-column>
              <el-table-column label="操作" width="90" fixed="right">
                <template slot-scope="scope">
                  <el-button
                    @click="handleDelete(scope.row)"
                    type="text"
                    size="small"
                    >删除</el-button
                  >
                  <el-button
                    @click="handleAdd(scope.row)"
                    type="text"
                    size="small"
                    >增加</el-button
                  >
                </template>
              </el-table-column>
            </el-table>
            <div class="order_total">
              <span><small>数量：</small>{{ totalCount }}</span>
              <span><small>金额：</small>{{ totalPrice }}元</span>
            </div>
            <div class="bottom_btn">
              <el-button type="warning" size="small">挂单</el-button>
              <el-button type="danger" size="small" @click="handleDelete(null)"
                >删除</el-button
              >
              <el-button type="success" size="small" @click="checkout()"
                >结账</el-button
              >
            </div>
          </el-tab-pane>
          <el-tab-pane label="挂单">挂单</el-tab-pane>
          <el-tab-pane label="外卖">外卖</el-tab-pane>
        </el-tabs>
      </el-col>
      <el-col :span="17">
        <div class="often_goods">
          <div class="often_goods_title">常点商品</div>
          <div class="often_goods_list">
            <ul>
              <li
                v-for="goods in goodsList"
                v-bind:key="goods.id"
                @click="handleAdd(goods)"
              >
                <span>{{ goods.name }}</span>
                <span>￥{{ goods.price }}元</span>
              </li>
            </ul>
          </div>
        </div>
        <div class="goods_type">
          <el-tabs type="border-card">
            <el-tab-pane label="汉堡">
              <ul>
                <li
                  v-for="goods in hamGoodsList"
                  :key="goods.id"
                  class="ham_goods"
                  @click="handleAdd(goods)"
                >
                  <div>
                    <img :src="goods.imgUrl" alt="" width="100" />
                  </div>
                  <div>
                    <div>
                      <div>{{ goods.name }}</div>
                      <div>{{ goods.price }}元</div>
                    </div>
                  </div>
                </li>
              </ul>
            </el-tab-pane>
            <el-tab-pane label="小食">小食</el-tab-pane>
            <el-tab-pane label="饮料">饮料</el-tab-pane>
            <el-tab-pane label="套餐">套餐</el-tab-pane>
          </el-tabs>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
// import axios from 'axios'
export default {
  name: 'Index',
  data() {
    return {
      totalCount: 0,
      totalPrice: 0,
      tableData: [],
      goodsList: [
        {
          id: 1,
          name: '酱烧肥牛米汉堡',
          price: 17
        },
        {
          id: 2,
          name: '香酥双鸡堡',
          price: 17
        },
        {
          id: 3,
          name: '黄金Q虾堡',
          price: 17
        },
        {
          id: 4,
          name: '菠萝鸡腿堡',
          price: 17
        },
        {
          id: 5,
          name: '辣味超级鸡腿堡',
          price: 17
        },
        {
          id: 6,
          name: '超级鸡腿堡',
          price: 17
        },
        {
          id: 7,
          name: '鲜虾米汉堡',
          price: 17
        }
      ],
      hamGoodsList: [
        {
          id: 1,
          imgUrl:
            'http://www.dicos.com.cn/Uploads/Picture/2018-10-12/5bc04023a03a0.png',
          name: '鲜虾米汉堡',
          price: 18
        },
        {
          id: 2,
          imgUrl:
            'http://www.dicos.com.cn/Uploads/Picture/2018-10-12/5bc04023a03a0.png',
          name: '超级鸡腿堡',
          price: 15
        },
        {
          id: 3,
          imgUrl:
            'http://www.dicos.com.cn/Uploads/Picture/2018-10-26/5bd2f11c80551.png',
          name: '和风汉堡',
          price: 15
        },
        {
          id: 4,
          imgUrl:
            'http://www.dicos.com.cn/Uploads/Picture/2018-10-12/5bc04135d7133.png',
          name: '快乐全家桶',
          price: 80
        },
        {
          id: 5,
          imgUrl:
            'http://www.dicos.com.cn/Uploads/Picture/2018-10-26/5bd2f11c80551.png',
          name: '脆皮炸鸡腿',
          price: 10
        },
        {
          id: 6,
          imgUrl:
            'http://www.dicos.com.cn/Uploads/Picture/2018-10-12/5bc04135d7133.png',
          name: '魔法鸡块',
          price: 20
        },
        {
          id: 7,
          imgUrl:
            'http://www.dicos.com.cn/Uploads/Picture/2018-10-26/5bd2f12ae07f5.png',
          name: '可乐大杯',
          price: 10
        },
        {
          id: 8,
          imgUrl:
            'http://www.dicos.com.cn/Uploads/Picture/2018-10-12/5bc04135d7133.png',
          name: '雪顶咖啡',
          price: 18
        }
      ]
    }
  },
  // 在created生命周期中请求后台接口
  // created() {
  //   axios('https://xxxxxxxxx')
  //     // 请求到的数据赋值给data中的tableData
  //     .then(res => (this.tableData = res.data))
  //     .catch(err => console.log(err))
  // },
  mounted() {
    const { clientHeight, clientWidth } = document.body
    document.getElementById('posOrder').style.height = `${clientHeight}px`
    document.getElementById('posMain').style.width = `${clientWidth - 70}px`
  },
  methods: {
    handleAdd(goods) {
      if (this.tableData.find(item => item.name === goods.name)) {
        this.tableData = this.tableData.map(item =>
          item.name === goods.name ? { ...item, count: item.count + 1 } : item
        )
      } else {
        let obj = { ...goods, count: 1 }
        this.tableData.push(obj)
      }
      this.calculateTotal(this.tableData)
    },
    handleDelete(goods) {
      if (goods) {
        this.tableData = this.tableData.filter(item => item.name !== goods.name)
        this.calculateTotal(this.tableData)
      } else {
        this.totalCount = 0
        this.totalPrice = 0
        this.tableData = []
      }
    },
    calculateTotal(arr) {
      this.totalCount = arr.reduce((total, item) => (total += item.count), 0)
      this.totalPrice = arr.reduce(
        (total, item) => (total += item.count * item.price),
        0
      )
    },
    checkout() {
      if (this.totalCount) {
        this.tableData = []
        this.totalCount = 0
        this.totalPrice = 0
        this.$message({
          message: '结账成功',
          type: 'success'
        })
      } else {
        this.$message.error('不能空结！')
      }
    }
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
.often_goods_list {
  height: 210px;
  overflow: auto;
  padding-bottom: 5px;
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
  background-color: #ffffff;
  cursor: pointer;
}
.often_goods_list ul li > span:last-child {
  color: #409eff;
  font-weight: bold;
  font-size: 16px;
  margin-left: 5px;
}
.goods_type ul {
  height: 300px;
  overflow: auto;
}
.ham_goods {
  border: 1px solid #d2d4da;
  border-radius: 5px;
  float: left;
  margin: 5px;
  width: 200px;
  height: 100px;
  cursor: pointer;
}
.ham_goods > div:first-child {
  float: left;
}
.ham_goods > div:last-child {
  float: left;
  display: flex;
  height: 100px;
  padding-left: 5px;
}
.ham_goods > div:last-child > div {
  margin: auto;
}
.order_total {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ebeef5;
  margin-top: -1px;
  padding-left: 10px;
  text-align: center;
}
.order_total > span:last-child {
  margin-left: 30px;
}
</style>
