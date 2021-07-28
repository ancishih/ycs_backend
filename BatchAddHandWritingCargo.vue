<template>
    <div style="">
        <h5 style="color:#689AE5;">新建貨單</h5>
        <button class="btn btn-sm btn-primary" data-toggle="modal" data-target="#editmodal">編輯</button>
        <div>
            <form id='data_info_han'>
                <div class="flexrow" style="width:2440px">
                    <div class="flexcol" style="margin:0 40px 0 0;">
                        <p>*選擇客戶</p>
                        <multi-select-customer-with-number-layout
                        @selectID="selectID"
                        :label-text="'選擇客戶'"
                        :prompt-text="'請選擇客戶'"
                        :data-api="get_customer_api" />
                    </div>
                    <div class="flexcol" style="width:150px;">
                        <label for="trackingNumber">*訂單編號</label>
                        <input type="text" style="width:150px;" name="trackingNumber" v-model="trackingNumber">
                    </div>
                    <div class="flexcol">
                        <label for="name">*收件者姓名</label>
                        <input type="text" style="width:90px;" name="name" v-model="name">
                    </div>
                    <div class="flexcol">
                        <label for="Address">*收件者地址</label>
                        <input type="text" name="Address" style="width:475px;" v-model="Address">
                    </div>
                    <div class="flexcol">
                        <label for="phone">*收件人電話</label>
                        <input type="text" style="width:130px;" name="phone" v-model="phone">
                    </div>
                    <div class="flexcol">
                        <label for="numOfPackage">*件數</label>
                        <input type="text" style="width:40px;" name="numOfPackage" v-model="numOfPackage">
                    </div>
                    <div class="flexcol">
                        <label for="size">*尺寸</label>
                        <input type="text" style="width:52px;" name="size" v-model="size">
                    </div>
                    <div class="flexcol">
                        <label for="weight">*重量</label>
                        <input type="text" style="width:52px;" name="weight" v-model="weight">
                    </div>
                    <div class="flexcol">
                        <label for="cargo_type">*貨物類型</label>
                        <select style="width:67px;" name="cargo_type" v-model="cargo_type">
                            <option value="文件">文件</option>
                            <option value="包裹">包裹</option>
                        </select>
                    </div>
                    <div class="flexcol" style="width:67px;">
                        <label for="paymentMethod">*運費到付</label>
                        <select style="width:52px;" name="paymentMethod" v-model="pay_radio">
                            <option value="1">是</option>
                            <option value="0">否</option>
                        </select>
                    </div>
                    <div class="flexcol">
                        <label for="paymentMethodIsY">*運費金額</label>
                        <input type="number" name="paymentMethodIsY" style="width:67px;">
                    </div>
                    <div class="flexcol" style="width:67px;">
                        <label for="collection">代收貨款</label>
                        <input type="number" name="collection" style="width:60px;" v-model="collection">
                    </div>
                    <div class="flexcol">
                        <label for="checkout_type">*結帳方式</label>
                        <select style="width:67px;" name="checkout_type" v-model="checkout_type">
                            <option value="現金">
                                現金
                            </option>
                            <option value="月結">
                                月結
                            </option>
                        </select>
                    </div>
                    <div class="flexcol">
                        <label for="checkoutTypeIsCash">*結帳金額</label>
                        <input type="number" name="checkoutTypeIsCash" style="width:67px;">
                    </div>
                    <div class="flexcol">
                        <label for="remarks">備註</label>
                        <input type="text" name="remarks" style="width:241px;" v-model="remarks">
                    </div>
                </div>
                <div class="flexrow" style="width:2440px;margin:20px 0 30px 0;">
                    <div class="flexrow items-center">
                        <label class="txt" for="sentcompany" style="width:64px">寄件公司</label>
                        <input type="text" style="width:307px;margin:0 20px 0 10px;" name="sentcompany" v-model="sentcompany">
                    </div>
                    <div class="flexrow items-center">
                        <label class="txt" for="sentname" style="width:80px">寄件人姓名</label>
                        <input type="text" style="width:194px;margin:0 20px 0 10px;" name="sentname" v-model="sentname">
                    </div>
                    <div class="flexrow items-center">
                        <label class="txt" for="sentphone" style="width:80px">寄件人電話</label>
                        <input type="text" style="width:130px;margin:0 20px 0 10px;" name="sentphone" v-model="sentphone">
                    </div>
                    <div class="flexrow items-center">
                        <label class="txt" for="company" style="width:64px">收件公司</label>
                        <input type="text" style="width:307px;margin:0 20px 0 10px;" name="company" v-model="company">
                    </div>
                    <div class="flexrow items-center">
                        <label class="txt" for="Productname" style="width:32px">品名</label>
                        <input type="text" style="width:307px;margin:0 20px 0 10px;" name="Productname" v-model="Productname">
                    </div>
                    <button class="btn btn-success" @click.prevent="submit">新增</button>
                </div>
            </form>
            <div style="width:2240px;border-bottom: 1px solid #C4C4C4;margin-bottom:30px;"></div>
        </div>
        <table style="width:2440px;">
            <thead>
                <tr>
                    <th>項次</th>
                    <th>單號</th>
                    <th>寄件公司</th>
                    <th>寄件人姓名</th>
                    <th>寄件人電話</th>
                    <th>收件公司</th>
                    <th>選擇客戶</th>
                    <th>訂單編號</th>
                    <th>收件者姓名</th>
                    <th>收件者地址</th>
                    <th>收件人電話</th>
                    <th>件數</th>
                    <th>尺寸</th>
                    <th>重量</th>
                    <th>貨物類型</th>
                    <th>運費到付</th>
                    <th>運費金額</th>
                    <th>代收貨款</th>
                    <th>結帳方式</th>
                    <th>結帳金額</th>
                    <th>狀態</th>
                    <th>品名</th>
                    <th>備註</th>
                    <th>動作</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td colspan="24" style="height:30px"></td>
                </tr>
                <!-- v-for -->
                <!-- v-for="(client,index) in clientGroup" :key="index" -->
                <tr v-for="(client,index) in clientGroup" :key="index">
                    <td>{{index+1}}</td>
                    <td>{{"單號"}}</td>
                    <td>{{client.sentcompany}}</td>
                    <td>{{client.sentname}}</td>
                    <td>{{client.sentphone}}</td>
                    <td>{{client.company}}</td>
                    <td>琺藍希絲</td>
                    <td>{{client.trackingNumber}}</td>
                    <td>{{client.name}}</td>
                    <td>{{client.Address}}</td>
                    <td>{{client.phone}}</td>
                    <td>{{client.numOfPackage}}</td>
                    <td>{{client.size}}</td>
                    <td>{{client.weight}}</td>
                    <td>{{client.cargo_type}}</td>
                    <td>{{client.paymentMethod?"是":"否"}}</td>
                    <td>{{client.paymentMethodIsY}}</td>
                    <td>{{client.collection}}</td>
                    <td>{{client.checkout_type}}</td>
                    <td>{{client.cash}}</td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td>
                        <button class="btn btn-sm btn-primary" data-toggle="modal" data-target="#editmodal">編輯</button>
                        <button class="btn btn-sm btn-danger" @click="deleteFormData(index)">刪除</button>
                    </td>
                </tr>
            </tbody>
        </table>
        <div class="modal" tabindex="-1" id="editmodal" aria-labelledby="editmodalLabel" aria-hidden="true">
            <div class="modal-dialog modal-lg modal-dialog-centered">
                <div class="modal-content">
                    <div class="modal-body">
                        <form>
                            <table class="edit_table">
                                <tbody >
                                    <tr>
                                        <td>
                                            <label for="">訂單編號</label>
                                        </td>
                                        <td>
                                            <input type="text">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <label for="">收件者姓名</label>
                                        </td>
                                        <td>
                                            <input type="text">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <label for="">收件者地址</label>
                                        </td>
                                        <td>
                                            <input type="text">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <label for="">收件人電話</label>
                                        </td>
                                        <td>
                                            <input type="text">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <label for="">件數</label>
                                        </td>
                                        <td>
                                            <input type="text">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <label for="">尺寸</label>
                                        </td>
                                        <td>
                                            <input type="text">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <label for="">重量</label>
                                        </td>
                                        <td>
                                            <input type="text">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <label for="">貨物類型</label>
                                        </td>
                                        <td>
                                            <input type="text">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <label for="">運費到付</label>
                                        </td>
                                        <td>
                                            <input type="text">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <label for="">代收貨款</label>
                                        </td>
                                        <td>
                                            <input type="text">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <label for="">結帳方式</label>
                                        </td>
                                        <td>
                                            <input type="text">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <label for="">結帳金額</label>
                                        </td>
                                        <td>
                                            <input type="text">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <label for="">寄件公司</label>
                                        </td>
                                        <td>
                                            <input type="text">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <label for="">寄件人姓名</label>
                                        </td>
                                        <td>
                                            <input type="text">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <label for="">寄件人電話</label>
                                        </td>
                                        <td>
                                            <input type="text">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <label for="">收件公司</label>
                                        </td>
                                        <td>
                                            <input type="text">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <label for="">品名</label>
                                        </td>
                                        <td>
                                            <input type="text">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <label for="">備註</label>
                                        </td>
                                        <td>
                                            <input type="text">
                                        </td>
                                    </tr>
                                </tbody>
                            </table>
                            <div class="d-flex col justify-content-center">
                                <button class="btn btn-success mx-4" @click.prevent="dummy">確認</button>
                                <button class="btn btn-danger" data-dismiss="modal">取消</button>
                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </div> 
    </div>
</template>
<script>
export default {
    name:'BatchAddHandWritingCargo',
    data(){
        return{
            dummy:"",
            clientGroup:[],
            dialog:false,
            errors:[],
            cargo_type:'',
            checkout_type:'',
            trackingNumber:'',
            pay_radio:'',
            get_customer_api:'/api/customer/belongCompanyByDomCustomer',
            select_id:0,
            select_city:'',
            select_site:'',
            select_road:'',
            sentcompany:'',
            sentname:'',
            sentphone:'',
            numOfPackage:'',
            size:'',
            weight:'',
            collection:'',
            collection_fee:"",
            Address:'',
            company:'',
            name:'',
            phone:'',
            Productname:'',
            remarks:''
        }
    },
    methods:{
        selectID: function (selectID) {
            this.select_id = selectID
        },
        resetForm:function(){
            this.cargo_type='',
            this.checkout_type='',
            this.trackingNumber='',
            this.pay_radio='',
            this.sentcompany='',
            this.sentname='',
            this.sentphone='',
            this.numOfPackage='',
            this.size='',
            this.weight='',
            this.collection='',
            this.collection_fee="",
            this.Address='',
            this.company='',
            this.name='',
            this.phone='',
            this.Productname='',
            this.remarks=''
        },
        setFormData(){

        },
        deleteFormData(index){
            this.clientGroup.splice(index,1)
        },
        submit:function(){
            let error_data = false
            let formValues = {}
            $.each($('#data_info_han').serializeArray(), function(i, field) {
                if(field.name != 'company' && field.name != 'remarks' && field.name != 'collection'  && field.name != 'collection_fee' && field.name != 'trackingNumber' && field.name != 'Productname'
                && field.name != 'sentphone' && field.name != 'sentname' && field.name != 'sentcompany' && field.name != 'paymentMethodIsY' && field.name != 'checkoutTypeIsCash'){
                    if(field.value == ''){
                        alert($(`#data_info_han label[for='${field.name}']`).text()+'為必填');
                        error_data = true;
                        return false;
                    }
                }
                formValues[field.name] = field.value;
            });
            if(!error_data){
                if(this.trackingNumber == ''){
                    alert('請輸入訂單編號');
                    error_data = true;
                }
            }
            if(!error_data){
                if(this.cargo_type == ''){
                    alert('請選擇貨物類型');
                    error_data = true;
                }
            }
            if(!error_data){
                if(this.checkout_type == ''){
                    alert('請選擇結帳方式');
                    error_data = true;
                }
            }
            if(!error_data){
                if(formValues['paymentMethod']==null){
                    alert('請選擇運費到付');
                    error_data = true;
                }
            }
            if(!error_data){
                if(formValues['paymentMethod'] == 1){
                    if(formValues['paymentMethodIsY'] == ''){
                        alert('運費金額為必填');
                        error_data = true;
                    }else{
                        formValues['paymentMethod'] = formValues['paymentMethodIsY'];
                    }
                }
            }
            if(!error_data){
                if(formValues['checkout_type'] == '現金'){
                    if(formValues['checkoutTypeIsCash'] == ''){
                        alert('請填寫結帳金額');
                        error_data = true;
                    }else{
                        formValues['cash'] = formValues['checkoutTypeIsCash'];
                    }
                }
            }
            if(!error_data){
                if(this.Address == ''){
                    alert('請填寫收件者地址');
                    error_data = true;
                }
            }
            if(!error_data){
                formValues['trackingNumber'] = this.trackingNumber;
                formValues['cargo_type'] = this.cargo_type;
                formValues['checkout_type'] = this.checkout_type;
                formValues['collection'] = (formValues['collection'] == null || formValues['collection'] == '' ) ? 0 :formValues['collection'];
                formValues['collection_fee'] = (formValues['collection_fee'] == null || formValues['collection_fee'] == '' ) ? 0 :formValues['collection_fee'];
                formValues['customers_id'] = this.select_id;
                formValues['address'] = formValues["Address"];
                formValues['isHandWriting'] = true;
                // console.log(formValues['Address'])
                axios.post("/api/ForecastUploadCargo/judgmentoreAddressFromHandWrite",{address:formValues['Address']})
                .then((response) => {
                    if (!response.data.success) {
                        this.clientGroup.push(formValues)
                        // location.reload();
                        this.resetForm();
                        formValues = {}
                    }
                })
                .catch(error => { console.log(error); });
            }
        },


    },
    watch:{
        'pay_radio':function(){
            if(this.pay_radio == 0){
                $('input[name="paymentMethodIsY"]').val('');
                $('input[name="paymentMethodIsY"]').attr('disabled',true);
            }else{
                $('input[name="paymentMethodIsY"]').attr('disabled',false);
            }
        },
        'checkout_type':function(){
            if(this.checkout_type != '現金'){
                $('input[name="checkoutTypeIsCash"]').val('');
                $('input[name="checkoutTypeIsCash"]').attr('disabled',true);
            }else{
                $('input[name="checkoutTypeIsCash"]').attr('disabled',false);
            }
        },
        'clientGroup':function(){
            console.log(this.clientGroup)
        }
    }
}
</script>
<style lang="scss" scoped>
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
.flexrow{
    display: flex;
    flex-direction:row;
    button{
        width:126px;
        height:34px;
        margin-left:81px;
    }
}
p{
    font-size:15px;
    line-height:18px;
    font-weight:400;
    color:#A5A2A2;
}
thead tr th{
    margin:0 25px 0 0;
    font-size:15px;
    line-height:18px;
    font-weight:400;
    color:#A5A2A2;
    padding:0;
}
tbody tr td{
    font-size:16px;
    line-height:18.75px;
    font-weight:400;
    color:#646363;
    margin:0;
    padding:0;

}
.edit_table tbody tr td label{
    width:150px;
    text-align:end;
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
</style>
