<template>
    <div id="join_case_wrap">
        <div class="join_case_box">
            <div class="join_case_title">
                <p>成功案例</p>
            </div>
            <div class="join_case_table">
                <table>
                    <tr>
                        <th>门店</th>
                        <th>开业时间</th>
                        <th>面积</th>
                        <th>投资金额</th>
                        <th>开店业绩</th>
                    </tr>
                    <tr>
                        <td class="join_case_table_title">广东•东莞</td>
                        <td>2015.9</td>	
                        <td>2000m2独栋生态生活馆</td>
                        <td>500万</td>
                        <td>278万</td>
                    </tr>
                    <tr>
                        <td class="join_case_table_title">江苏•南京</td>
                        <td>2017.1</td>	
                        <td>1200m2独立专卖店</td>
                        <td>480万</td>
                        <td>725万</td>
                    </tr>
                    <tr>
                        <td class="join_case_table_title">四川•成都</td>
                        <td>2017.8</td>	
                        <td>2400m2独立四层生态生活馆</td>
                        <td>850万</td>
                        <td>1893万</td>
                    </tr>
                    <tr>
                        <td class="join_case_table_title">内蒙古•包头</td>
                        <td>2018.1</td>	
                        <td>500m2独立专卖店</td>
                        <td>183万</td>
                        <td>127万</td>
                    </tr>
                </table>
            </div>
            <div class="join_case_img"><img src="~/assets/images/join/join_case_img.png"></div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'joinCase'
    }
</script>

<style scoped>
    div#join_case_wrap {
        width:  100%;
        background: #f9f9fa;
    }

    .join_case_box {
        width:  100%;
        padding: 0 0.267rem 1.387rem 0.187rem;
        box-sizing:  border-box;
        text-align:  center;
    }

    .join_case_title {
        width:  100%;
        padding: 1rem 0 0.173rem;
        font-size: 0.32rem;
        font-weight: bold;
        line-height: 0.667rem;
        color: #22202b;
    }

    .join_case_table {
        width: 100%;
    }

    .join_case_table table {
        width: 100%;
    }

    .join_case_table table tr {
        width: 100%;
        height: 0.6rem;
        font-size: 0.24rem;
        line-height: 0.6rem;
        color: #22202b;
        text-align:  center;
    }

    .join_case_table table tr th {
        font-weight:  bold;
        text-align:  center;
        border: 0.04rem solid #000;
    }

    .join_case_table table tr td.join_case_table_title {
        color: #22202b;
        font-weight: bold;
    }

    .join_case_table table tr td {
        font-size: 0.24rem;
        line-height: 0.6rem;
        color: #22202b;
        border: 0.04rem solid #000;
    }

    .join_case_img {
        overflow:  hidden;
        width: 8.68rem;
        height: 5.587rem;
        margin: 1.44rem 0.96rem 0 0.36rem;
    }

    .join_case_img img {
        width:  100%;
    }
</style>


