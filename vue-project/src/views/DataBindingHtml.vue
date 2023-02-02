<template>
    <div>
        <div>{{ htmlString }}</div>
        <div v-html="htmlString"></div>
        <h1>Hello, {{title }}!</h1>
        <input type="text" v-model="valueModel" />
        <div><input type="number" v-model.number="numberModel"></div>
        <div><textarea  v-model="message"></textarea></div>
        <div>
            <select name="" id="" v-model="city">
                <option value="02">서울</option>
                <option value="21">부산</option>
                <option value="064">제주</option>
            </select>
        </div>
        <div><input type="checkbox" v-model="chk" true-value="yes" false-value="no">{{ chk }}</div>
        <div>
            <label><input type="checkbox" value="서울23" v-model="checked2">서울</label>
            <label><input type="checkbox" value="부산" v-model="checked2">부산</label>
            <label><input type="checkbox" value="제주" v-model="checked2">제주</label>
            <br>
            <span>체크한 지역 : {{ checked2 }}</span>
        </div>
        <div>
            <label><input type="radio" v-bind:value="radioValue1" v-model="picked">서울</label>
            <label><input type="radio" v-bind:value="radioValue2" v-model="picked">부산</label>
            <label><input type="radio" v-bind:value="radioValue3" v-model="picked">제주</label><br>
            <span>선택한 지역 : {{ picked }}</span>
        </div>
        <div><img v-bind:src="imgSrc" alt=""/></div>
        <div>
            <input type="text" v-model="textValue" />
            <button type="button" v-bind:disabled="textValue==''">Click</button>
        </div>
        <div class="container" v-bind:class="{'active': isActive, 'text-red': hassError}">Class Binding</div>
        <div v-for="(item, index) in items"></div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                htmlString: '<p style="color:red;">This a red string.</p>',
                title: 'world',
                valueModel : 'South Korea',
                numberModel: '111',
                message : '여러줄을 입력할 수 있는 textarea 입니다',
                city : '064',
                chk : 'yes',
                checked2 : [],
                picked: '',
                radioValue1 : '서울1',
                radioValue2 : '부산',
                radioValue3 : '제주',
                imgSrc : '../assets/logo.png',
                textValue : '',
                isActive : true,
                hassError : false
            };
        }
    }
</script>
<style scoped>
    container {width:100%;height:200px;}
    .active{background-color: yellow; font-weight:bold;}
    .text-red{color:red}
</style>