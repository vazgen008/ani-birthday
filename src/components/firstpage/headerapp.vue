<template>
<img src="./img/anibg.jpg" alt="" class="background">
<img src="./img/anibg.jpg" alt="" class="respbg">
    <div class="wedding__invitation">
        <div class="wedding__invitation--info invitation__info">
            <div class="languageAction">
            <button class="language" @click="$i18n.locale = $i18n.locale === 'am' ? 'en' : 'am'">{{$i18n.locale}} | {{$i18n.locale == 'am' ? 'en':'am'}}</button> 
            </div>
            <div class="invitation__info--header">
                <h1>{{ $t('title') }}</h1>
            </div>
            <div class="invitation__info--names" v-if="$i18n.locale === 'am'">
                <img src="https://static.tildacdn.one/tild3132-3965-4765-b164-643561323563/01.svg" class="circle" alt="">
                <img src="./img/rings (2).png" class="wedding--rings" alt="">
                <h1 class="name--artur">{{ $t('title') }}</h1>
                <h1 class="name--liana">{{ $t('title2') }}</h1>
                
            </div>
            <div class="invitation__info--names" v-else>
                <img src="https://static.tildacdn.one/tild3132-3965-4765-b164-643561323563/01.svg" class="circle" alt="">
                 <img src="./img/rings (2).png" class="wedding--rings" alt="">
                <h1 class="name--artur">{{ $t('title') }}</h1>
                <h1 class="name--liana">{{ $t('title2') }}</h1>
                
            </div>
            
        </div>
        <MainInfo/>
    </div>
</template>


<script setup>
import MainInfo from './MainInfo.vue'
</script>


<style scoped lang="scss"> 
.respbg{
    opacity: 0;
        width: 100%;
    height: 100%;
}
.background{
    position: fixed;
        width: 100%;
    height: 100%;
}
*{
    margin: 0 0;
}
.wedding--rings{
    position: absolute;
    width: 100px;
    top: 17px;
            animation: nameanimation 4s linear forwards;

}
.wedding__invitation{
    width: 100%;
    height: auto;
    z-index: 10;
    position: absolute;
    top: 0;
    &--info{
        height: 700px;
        background: none;
        color: white;
    }
}
.invitation__info{
     padding-top: 40px; 
    &--header{
        font-family: "MontserratARM", Arial, sans-serif;
        font-weight: 300;
        line-height: 37px;
        text-align: center;
     color: #9a780b;

    &h1{
        padding-left: 320px;
        width: 560px;
        zoom: 1.122;
    }
    }
    & .language{
            width: 108px;
            height: 23px;
            text-transform: uppercase;
            border-width: 1px;
            border-radius: 10px;
            background: none;
            background-position: center center;
            border-color: black;
            border-style: solid;
            transition: background-color 0.3s ease-in-out, color 0.3s ease-in-out, border-color 0.3s ease-in-out;

            color: black;
            margin-bottom: 6px;
            margin-left: 120px;
        }
    &--names{
     color: #9a780b;

        padding-top: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
        & .circle{
            width: 250px;
            zoom: 1.122;
            animation: namesAnimation 2.4s linear forwards;
            backface-visibility: hidden;
        transform: rotate(6deg);
    position: relative;

        }
        & .name--artur{
            // left: 601px;
            margin-right: 50px;
            top: 110px;
            width: auto;
            zoom: 1.122;
            position: absolute;
            animation: nameanimation 1.6s linear forwards;
            backface-visibility: hidden;
        }
         & .name--liana{
            // left: 620px;
            margin-left: 50px;

            top: 160px;
            width: 120px;
            zoom: 1.122;
            position: absolute;
            animation: nameanimation 2s linear forwards;
            backface-visibility: hidden;
        }
    }
    &--countdown{
            display: flex;
    padding-top: 33px;
    flex-direction: column;
    align-items: center;
    row-gap: 20px;
    font-family: 'MontserratARM';
    font-weight: 300;

    & img{
        margin-top: 30px;
        animation: ArrowUpDown 2.6s infinite linear;
        backface-visibility: hidden;
        width: 42px;
        height: 21px;
        cursor: pointer;
    }
    & h1{
        font-size: 28px;
    }
    }
}



// animation: sbs-711855695-1681992064612 2.4s linear forwards;
//     backface-visibility: hidden;
//     transform: rotate(6deg);
@keyframes namesAnimation {
    0% {
    opacity: 0;
    transform: scale(1, 1);
    animation-timing-function: linear;
}
1% {
    opacity: 0;
    transform: scale(0.75, 0.75);
    animation-timing-function: linear;
}
59% {
    opacity: 0;
    transform: scale(0.75, 0.75);
    animation-timing-function: cubic-bezier(0.34,1.61,0.7,1);
}
100% {
    opacity: 1;
    transform: scale(1, 1);
}
}


@keyframes nameanimation {

0% {
    opacity: 0;
    transform: scale(1, 1);
    animation-timing-function: linear;
}
1% {
    opacity: 0;
    transform: scale(0.75, 0.75);
    animation-timing-function: linear;
}
38% {
    opacity: 0;
    transform: scale(0.75, 0.75);
    animation-timing-function: cubic-bezier(0.34,1.61,0.7,1);
}
100% {
    opacity: 1;
    transform: scale(1, 1);
}

}


@keyframes ArrowUpDown {
    0% {
        transform: translateY(0px);
        animation-timing-function: ease-in;
    }
    50% {
        transform: translateY(15px);
        animation-timing-function: ease-in;
    }
    100% {
        transform: translateY(0px);
    }
}


@media only screen and (min-width: 375px) and (max-width: 600px) {
    .background{
        display: none;
    }
    .respbg{
         opacity: 1;
        position: fixed;
            width: 100%;
    height: 100%;
    }
    
  .invitation__info {
    &--header{
       
        padding-left: 0;
        padding-top: 0;
        & h1{
            padding-left: 0;
            width: auto;    
        }
    }
    & .languageAction{
        text-align: center;
        & button{
            margin: 0 0 20px 0
            ;
        }
    }

  }
}
/*
<h1>{{ $t('title') }}</h1>
    <button @click="$i18n.locale = this.$i18n.locale === 'am' ? 'ru' : 'am'">{{$i18n.locale}} | {{$i18n.locale == 'am' ? 'ru':'am'}}</button> 
 */
</style>
