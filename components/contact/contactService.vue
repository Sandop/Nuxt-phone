<template>
    <div id="customer_service_wrap">
        <div class="customer_service_box clearfix">
            <div class="customer_service_title">
                <p class="customer_service_titleC">客户服务</p>
                <p class="customer_service_titleE">Customer service</p>
            </div>
            <div class="customer_service_left">
                <div class="customer_service_content">
                    <div class="customer_service_content_title">客户</div>
                    <div class="customer_service_content_box">
                        <ul>
                            <li class="customer_service_list">
                                <p class="customer_service_list_contact">400-900-6267</p>
                                <p class="customer_service_list_name">24小时热线</p>
                            </li>
                            <li class="customer_service_list">
                                <p class="customer_service_list_contact">186-2366-5691</p>
                                <p class="customer_service_list_name">售后服务</p>
                            </li>
                            <li class="customer_service_list">
                                <p class="customer_service_list_contact">Service@visney.cn</p>
                                <p class="customer_service_list_name">联系邮箱</p>
                            </li>
                        </ul>
                    </div>
                </div>
                <div class="customer_service_content">
                    <div class="customer_service_content_title">加入卫诗理</div>
                    <div class="customer_service_content_box">
                        <ul>
                            <li class="customer_service_list">
                                <p class="customer_service_list_contact">Service@visney.cn</p>
                                <p class="customer_service_list_name">简历投递</p>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
            <div class="customer_service_right">
                <div class="customer_service_content">
                    <div class="customer_service_content_title">业务合作</div>
                    <div class="customer_service_content_box">
                        <ul>
                            <li class="customer_service_list">
                                <p class="customer_service_list_contact">400-900-6267</p>
                                <p class="customer_service_list_name">加盟热线</p>
                            </li>
                            <li class="customer_service_list">
                                <p class="customer_service_list_contact">173-0263-3888</p>
                                <p class="customer_service_list_name">招商联系人Penny</p>
                            </li>
                        </ul>
                    </div>
                </div>
                <div class="customer_service_content">
                    <div class="customer_service_content_title">知识产权事务建议/投诉/举报</div>
                    <div class="customer_service_content_box">
                        <ul>
                            <li class="customer_service_list">
                                <p class="customer_service_list_contact">Law@visney.cn</p>
                                <p class="customer_service_list_name">信息投递</p>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'contactService'
    }
</script>
<style>
    div#customer_service_wrap {
        width:  100%;
        padding: 0 0.32rem 1.347rem;
        box-sizing: border-box;
    }

    .customer_service_box {
        width: 100%;
        border-bottom: 0.027rem solid #e5e5e5;
    }

    .customer_service_title {
        width:  100%;
        padding:  1.44rem 0 0.64rem;
        text-align:  center;
        border-bottom: 0.027rem solid #e5e5e5;
    }

    p.customer_service_titleC {
        font-size: 0.4rem;
        font-weight: bold;
        line-height: 0.667rem;
        color: #22202b;
    }

    p.customer_service_titleE {
        font-size: 0.24rem;
        line-height: 0.44rem;
        color: #cccccc;
    }

    .customer_service_left {
        float:  left;
        width: 50%;
    }

    .customer_service_right {
        float:  right;
        width: 50%;
    }

    .customer_service_content {
        width: 100%;
        padding-left:  0.453rem;
        box-sizing:  border-box;
    }

    .customer_service_content_title {
        width:  100%;
        height: 1.2rem;
        padding: 0.867rem 0 0.667rem;
        font-family: MicrosoftYaHei-Bold;
        font-weight:  bold;
        font-size: 0.4rem;
        line-height: 0.6rem;
        color: #22202b;
    }

    .customer_service_content_box {
        width: 100%;
        min-height: 4.56rem;
    }

    .customer_service_content_box ul {
        width: 100%;
    }

    li.customer_service_list {
        width:  100%;
        padding-bottom: 0.507rem;
    }

    p.customer_service_list_contact {
        font-size: 0.4rem;
        line-height: 0.44rem;
        color: #22202b;
    }

    p.customer_service_list_name {
        margin-top: 0.133rem;
        font-size: 0.32rem;
        line-height: 0.44rem;
        color: #cccccc;
    }

    .customer_service_left .customer_service_content:last-child .customer_service_content_box {
        min-height: 1.52rem;
    }

    .customer_service_right .customer_service_content:last-child .customer_service_content_box {
        min-height: 1.52rem;
    }
</style>


