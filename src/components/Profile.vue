<template>
    <div class="profile root__section">
      <div class="user-info">
        <div class="user-info__photo"></div>
        <div class="user-info__data">
          <h1 class="user-info__name">Roman Lee</h1>
          <p class="user-info__job">Frontend</p>
        </div>
        <button 
        v-on:click="$emit('open-popup')"
        class="button user-info__button">+</button>
        <button class="button user-info__edit-button">Edit</button>
      </div>
    </div>
</template>



<style>
.profile {
    min-height: 300px;
    display: flex;
    align-items: center;
}


.user-info {
    display: flex;
    position: relative;
    align-items: flex-start;
    color: #fff;
    width: 100%;
}

.user-info__photo {
    width: 150px;
    height: 150px;
    min-width: 150px;
    border-radius: 50%;
    background-size: cover;
    background-position: 50%;
    background-image: url(../assets/avatar.jpg);
}

.user-info__data {
    max-width: 364px;
    margin-left: 36px;
}

.user-info__name {
    margin: 0;
    font-weight: 400;
    font-size: 54px;
    line-height: 56px;
}

.user-info__job {
    margin: 20px 0 0;
    font-size: 20px;
    line-height: 25px;
}

.button {
    background-color: transparent;
    border: 1px solid #fff;
    color: #fff;
    width: 150px;
    height: 50px;
    font-size: 30px;
    display: block;
    cursor: pointer;
}

.user-info__button {
    position: absolute;
    top: 16px;
    right: 0;
}

.user-info__edit-button {
    position: absolute;
    left: 187px;
    top: 168px;
    width: 38px;
    height: 18px;
    font-size: 12px;
    line-height: 15px;
    align-items: center;
    text-align: center;
}
</style>