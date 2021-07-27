<template >
    <div style="">
        <h5 style="color:#689AE5;">新建貨單</h5>
        <div>
            <form action="">
                <div class="flexrow" style="width:2440px">
                    <div class="flexcol" style="margin:0 40px 0 0;">
                        <p>*選擇客戶</p>
                        <select>
                            <option value="創力測試">創力測試</option>
                            <option value="創力測試">創力測試</option>
                            <option value="創力測試">創力測試</option>
                        </select>
                    </div>
                    <div class="flexcol" style="width:150px;">
                        <p>*訂單編號</p>
                        <input type="text" style="width:150px;">
                    </div>
                    <div class="flexcol">
                        <p>*收件者姓名</p>
                        <input type="text" style="width:90px;">
                    </div>
                    <div class="flexcol">
                        <p>*收件者地址</p>
                        <input type="text" style="width:475px;">
                    </div>
                    <div class="flexcol">
                        <p>*收件人電話</p>
                        <input type="text" style="width:130px;">
                    </div>
                    <div class="flexcol">
                        <p>*件數</p>
                        <input type="text" style="width:40px;">
                    </div>
                    <div class="flexcol">
                        <p>*尺寸</p>
                        <input type="text" style="width:52px;">
                    </div>
                    <div class="flexcol">
                        <p>*重量</p>
                        <input type="text" style="width:52px;">
                    </div>
                    <div class="flexcol">
                        <p>*貨物類型</p>
                        <select style="width:67px;"></select>
                    </div>
                    <div class="flexcol" style="width:67px;">
                        <p>*運費到付</p>
                        <select style="width:52px;"></select>
                    </div>
                    <div class="flexcol">
                        <p>*運費金額</p>
                        <input type="text" style="width:67px;">
                    </div>
                    <div class="flexcol" style="width:67px;">
                        <p>代收貨款</p>
                        <input type="text" style="width:60px;">
                    </div>
                    <div class="flexcol">
                        <p>*結帳方式</p>
                        <select style="width:67px;"></select>
                    </div>
                    <div class="flexcol">
                        <p>*結帳金額</p>
                        <input type="text" style="width:67px;">
                    </div>
                    <div class="flexcol">
                        <p>備註</p>
                        <input type="text" style="width:241px;">
                    </div>
                </div>
                <div class="flexrow" style="margin:20px 0 30px 0">
                    <div class="flexrow items-center">
                        <p class="txt" style="width:64px">寄件公司</p>
                        <input type="text" style="width:307px;margin:0 20px 0 10px;">
                    </div>
                    <div class="flexrow items-center">
                        <p class="txt" style="width:80px">寄件人姓名</p>
                        <input type="text" style="width:194px;margin:0 20px 0 10px;">
                    </div>
                    <div class="flexrow items-center">
                        <p class="txt" style="width:80px">寄件人電話</p>
                        <input type="text" style="width:130px;margin:0 20px 0 10px;">
                    </div>
                    <div class="flexrow items-center">
                        <p class="txt" style="width:64px">收件公司</p>
                        <input type="text" style="width:307px;margin:0 20px 0 10px;">
                    </div>
                    <div class="flexrow items-center">
                        <p class="txt" style="width:32px">品名</p>
                        <input type="text" style="width:307px;margin:0 20px 0 10px;">
                    </div>
                    <button class="">新增</button>
                </div>
            </form>
        </div>
        <table>

        </table>
    </div>
</template>
<script>
export default {
    name:"BatchAddHandWritingCargo",
}
</script>
<style lang="scss" scoped>
.flexrow{
    display: flex;
    flex-direction:row;
}
.flexcol{
    display: flex;
    flex-direction:column;
    margin:0 10px;
}
.items-center{
    align-items: center;
}
.txt{
    color: #646363;
    font-size:16px;
    line-height:18.75px;
    font-weight:500;
    margin:0;
}
p{
    font-size:15px;
    line-height:18px;
    font-weight:400;
    color:#A5A2A2;
}
select{
    width:95px; 
    height:34px;
    border:1px solid #C4C4C4;
    border-radius:5px
}
input{
    width:95px; 
    height:34px;
    border:1px solid #C4C4C4;
    border-radius:5px;
}
button{
    border-radius:5px;
    border:none;
    text-align:center;
    color:white;
    font-size:14px;
    line-height: 16px;
    font-weight:400;
}
.success{
    width:126px!important;
    height:34px;
    margin-left:84px;
}
</style>
