<template>
    <div id="place_address_wrap">
        <div class="place_address_box">
            <div class="place_address_details">
                <h3>体验店地址：</h3>
                <p v-for="(list,index) in addressData.addressDetils" :key="index">{{list}}</p>
            </div>
            <div class="place_address_phone">
                <div class="place_address_phone1">
                    <p>{{addressData.hotLineTitle}}</p>
                    <h3>{{addressData.hotLineNum}}</h3>
                </div>
                <div class="place_address_phone1">
                    <p>{{addressData.phoneTitle}}</p>
                    <h3>{{addressData.phoneNum}}</h3>
                </div>
            </div>
            <div class="place_address_contact">
                <p>为了保证您参观的尊贵体验，来时请提前预约</p>
                <div class="place_address_contact_num">
                    <h3>{{addressData.contentNum}}</h3>
                    <p>{{addressData.contentPeople}}</p>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'expericeAddress',
        props: {
            addressData: Object
        }
    }
</script>
<style>
    div#place_address_wrap {
        width:  100%;
    }

    .place_address_box {
        width:  100%;
        padding-bottom: 1.307rem;
    }

    .place_address_details {
        width:  100%;
        padding: 1.347rem 0.373rem 0.813rem;
        box-sizing:  border-box;
        border-bottom: 0.027rem solid #e5e5e5;
    }

    .place_address_details h3 {
        margin-bottom: 0.413rem;
        font-size: 0.4rem;
        font-weight: bold;
        line-height: 0.64rem;
        color: #25232d;
    }

    .place_address_details p {
        font-size: 0.32rem;
        line-height: 0.4rem;
        color: #858585;
    }

    .place_address_phone {
        display:  flex;
        width: 100%;
        padding: 0.773rem 0.373rem;
        box-sizing: border-box;
        border-bottom: 0.027rem solid #e5e5e5;
        justify-content: center;
        align-items:  center;
    }

    .place_address_phone1 {
        width:  50%;
    }

    .place_address_phone1 p {
        font-size: 0.32rem;
        line-height: 0.32rem;
        color: #858585;
    }

    .place_address_phone1 h3 {
        margin-top: 0.12rem;
        font-size: 0.533rem;
        font-weight: bold;
        line-height: 0.6rem;
        color: #25232d;
    }

    .place_address_contact {
        width: 100%;
        padding: 0.773rem 0.373rem;
        box-sizing: border-box;
        border-bottom: 0.027rem solid #e5e5e5;
    }

    .place_address_contact p {
        font-size: 0.32rem;
        line-height: 0.6rem;
        color: #858585;
    }

    .place_address_contact_num {
        display:  flex;
        margin-top: 0.12rem;
        font-size: 0.32rem;
        line-height: 0.32rem;
        color: #858585;
    }

    .place_address_contact_num h3 {
        font-size: 0.533rem;
        font-weight: bold;
        line-height: 0.6rem;
        color: #25232d;
    }
</style>
