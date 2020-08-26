<template>
<div>
    <el-steps :active="active" finish-status="success" simple style="margin-top: 10px">
        <el-step title="介绍"></el-step>
        <el-step title="连接"></el-step>
        <el-step title="开始"></el-step>
    </el-steps>
    <div style="text-align: left;margin-top: 40px;margin-left: 100px">
        <el-container>
            <el-aside width="200px">
                <img src="../assets/SimPre.png" height="400" width="200" />
            </el-aside>
            <el-main>
                <div style="margin-left: 100px">
                    <div v-show="active === 0">
                        <h1>SimPre是什么？</h1>
                        <p>SimPre是基于<a href="https://www.simplechain.com/" target="_blank" style="color: cornflowerblue"><strong>SimpleChain</strong></a>区块链智能合约的<strong>投票预测平台</strong>。
                        </p>
                        <p>旨在于提供一个去中心化的数据交互方式，用户的投票纪录将<strong>不可篡改</strong>地保存在SimpleChain区块链中。</p>
                        <p>用户在有<strong>成本制约</strong>的投票行为下，投票结果将对预测事件未来发展具有可靠的参考意义。</p>
                        <p style="color: #ff3508">注：平台采用SimPlug插件在国内网络环境接入SimpleChain。</p>
                        <p style="color: #ff3508">如不方便安装，可直接访问左侧<strong style="color: black">概览</strong>查看演示事件</p>
                        <el-button style="margin-top: 12px;" type="warning" @click="next">下一步</el-button>
                    </div>
                    <div v-show="active === 1">
                        <h1>连接区块链</h1>
                        <p>SimPre使用<a href="https://www.simplechain.com/developer" target="_blank" style="color: #ff7f51"><strong>SimPlug</strong></a>浏览器插件作为网页(Web3.js)与SimpleChain区块链的通信桥梁。
                        </p>
                        <p>在浏览器安装SimPlug后，使用SimPlug生成一个SimpleChain账号并选择<strong>测试网络</strong>。</p>
                        <p>任何写入SimpleChain区块链数据的操作都需要支付SIPC手续费，因此可在<a href="https://faucet.sipc.vip/" target="_blank" style="color: #ff7f51"><strong>水龙头</strong></a>中获取用于测试的SIPC。
                        </p>
                        <el-button style="margin-top: 12px;" type="success" @click="active = 0">返回上一步</el-button>
                        <el-button style="margin-top: 12px;" type="warning" @click="next">下一步</el-button>
                    </div>
                    <div v-show="active === 2">
                        <h1>开始投票</h1>
                        <p>点击<strong style="color:cornflowerblue">网页右上角头像</strong>使用SimPlug对SimPre进行操作授权，随后可<strong>创建预测平台账户</strong>。</p>
                        <p>此时SimPre将展示区块链的所有投票事件信息，用户可选择事件进行投票。</p>
                        <p>如果部分用户的投票选择与事件最终的<strong>实际结果一致</strong>，便能按比例分配奖池中的代币。</p>
                        <p>用户同时可<strong>消耗</strong>一定数量代币创建一个事件发布给全体用户进行投票。</p>
                        <p>SimPre的所有投票数据均在<strong style="color:cornflowerblue">SimpleChain</strong>公开给任何机构和个人用于事件预测。
                        </p>
                        <el-button style="margin-top: 12px;" type="success" @click="active = 1">返回上一步</el-button>
                    </div>
                </div>
            </el-main>
        </el-container>
    </div>
</div>
</template>

<script>
export default {
    data() {
        return {
            active: 0
        };
    },

    methods: {
        next() {
            if (this.active++ > 2) this.active = 0;
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style lang="stylus" scoped>
h1 {
    font-size: 32px
}

p {
    font-size: 16px
}
</style>
