<template>
    <div class="Wrapper large-img" style="margin-bottom:20px">
        <b-container>
            <b-row class="Wrap_Link">

                <b-col class="Link_In col-4 col-md-2">
                <a href="/#about" title="利用案内">
                    <div>
                    <img src="https://i.ibb.co/mvycm8s/link02-1.png" alt="利用案内">
                    </div>
                    <span>利用案内</span>
                </a>
                </b-col>

                <b-col class="Link_In col-4 col-md-2">
                <a href="/#activities" title="活動内容">
                    <div>
                    <img src="https://i.ibb.co/cTFKtdP/link02-1.png" alt="活動内容">
                    </div>
                    <span>活動内容</span>
                </a>
                </b-col>

                <b-col class="Link_In col-4 col-md-2">
                <a href="/#monthly_event" title="月間行事">
                    <div>
                    <img src="https://i.ibb.co/Dz166Ss/link03.png" alt="月間行事">
                    </div>
                    <span>月間行事</span>
                </a>
                </b-col>

                <b-col class="Link_In col-4 col-md-2">
                <a href="https://liff.line.me/1656795338-RBqjPVdy" title="混雑確認/予約">
                    <div>
                    <img src="https://i.ibb.co/8X4nK8f/link04.png" alt="混雑確認/予約">
                    </div>
                    <span>混雑確認/予約</span>
                </a>
                </b-col>

                <b-col class="Link_In col-4 col-md-2">
                <a href="/#news" title="ニュース">
                    <div>
                    <img src="https://i.ibb.co/SK5SJ1G/link02-1.png" alt="ニュース">
                    </div>
                    <span>ニュース</span>
                </a>
                </b-col>

                <b-col class="Link_In col-4 col-md-2">
                <a href="/" title="お問合せ">
                    <div>
                    <img src="https://i.ibb.co/YTv4cr4/link06.png" alt="お問合せ">
                    </div>
                    <span>お問合せ</span>
                </a>
                </b-col>
                
            </b-row>
        </b-container>
    </div>
</template>

<script>
  import MyButtons from '@/components/MyButtons'
  export default {
components: {
  MyButtons,
    }
}
</script>

<style scoped>
.Wrapper {
    padding: 0px;
    background-color: #4CAF50;
}

.Wrap_Link {
    display: flex;
    height: 100%;
    font-size: 16px;
    text-align: center;
    letter-spacing: -1px;
    padding-right: 20px;
    padding-left: 20px;
}

.Link_In {
    background-color: #4CAF50;
    padding-left: 5px;
    padding-right: 5px;
    padding-top: 15px;
    padding-bottom: 15px;
    align-self:center;
}

.Link_In a div {
    padding-bottom: 10px;
}

.Link_In a {
    color: #fff;
}


@media (max-width: 480px) {
    .Link_In {
    padding-top: 10px;
    padding-bottom: 10px;
    }

    .Link_In a div img {
    width: 60px;
    height: 60px;
    }
}


</style>