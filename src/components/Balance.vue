<script setup>

</script>
<template>
    <div class="balance">
        <div class="text">
            <p class="title">My Balance</p>
            <span class="total-balance">$921.48</span>
        </div>
        <div class="logo">
            <img src="../../images/logo.svg" alt="logo" class="logo-img">
        </div>
    </div>
</template>
<style scoped>
.balance {
    margin: 0 auto;
    width: 100%;
    max-width: 390px;
    padding: 20px;
    background: hsl(10, 79%, 65%);
    border-radius: 10px;
    display: flex;
    justify-content: space-between;
}

.text .title {
    color: hsl(27, 66%, 92%);
    font-size: .9rem;
    line-height: 17px;
}

.text .total-balance {
    color: hsl(27, 66%, 92%);
    font-weight: 700;
    font-size: 1.4rem;
}

.logo {
    height: 100%;
    display: flex;
    align-items: center;
}

.logo-img {
    width: 60Fpx;
}
</style>