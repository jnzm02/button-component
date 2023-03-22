<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import MyButton from './components/MyButton.vue'
</script>

<template>
  <div id="app" style="font-family: sans-serif">
    <div>
      <div class="left-bar">
        <div class="top-word"><span style="color: #F7542E; font-weight: bold;">Dev</span>Challenges.io</div>
        <div class="options">
          <div class="option">Colors</div>
          <div class="option">Typography</div>
          <div class="option">Spaces</div>
          <div class="option">Buttons</div>
          <div class="option selected-option">Inputs</div>
          <div class="option">Grid</div>
        </div>
      </div>
    </div>
    <div class="main">
      
      <div class="main-body">
        <div class="main-header">Buttons</div>
        <div class="buttons events">
          <div class="button">
            <div class="description">{{`< Button />`}}</div>
            <MyButton label="Default"/>
          </div>
          <div class="button">
            <div class="description">{{`< Button />`}}</div>
            <MyButton label="Default" style="background-color: #AEAEAE"/>
          </div>
          <div class="button">
            <div class="description">{{`< Button />`}}</div>
            <MyButton label="Default" variant="outline"/>
          </div>
          <div class="button">
            <div class="description">{{`< Button />`}}</div>
            <MyButton label="Default" variant="outline" style="background: #2962FF1A"/>
          </div>
          <div class="button">
            <div class="description">{{`< Button />`}}</div>
            <MyButton label="Default" variant="text"/>
          </div>
          <div class="button">
            <div class="description">{{`< Button />`}}</div>
            <MyButton label="Default" variant="text" style="background: #2962FF1A" />
          </div>
          <div class="button">
            <div class="description">{{`< Button />`}}</div>
            <MyButton label="Default" disableShadow/>
          </div>
        </div>
        <div class="buttons disabled">
          <div class="button">
            <div class="description">{{`<Button disabled />`}}</div>
            <MyButton label="Disabled" disabled />
          </div>
          <div class="button">
            <div class="description">{{`<Button variant=”text” disabled />`}}</div>
            <MyButton label="Disabled" variant="text" disabled />
          </div>
        </div>
        <div class="inline-buttons icons">
          <div class="button">
            <div class="description">{{`<Button startIcon=”local_grocery_store” />`}}</div>
            <MyButton label="Default" startIcon="local_grocery_store"/>
          </div>
          <div class="button">
            <div class="description">{{`<Button startIcon=”local_grocery_store” />`}}</div>
            <MyButton label="Default" endIcon="local_grocery_store"/>
          </div>
        </div>
        <div class="inline-buttons size">
          <div class="button">
            <div class="description">{{`<Button size=”sm” />`}}</div>
            <MyButton label="Default" size="sm"/>
          </div>
          <div class="button">
            <div class="description">{{`<Button size=”md” />`}}</div>
            <MyButton label="Default" size="md"/>
          </div>
          <div class="button">
            <div class="description">{{`<Button size=”lg” />`}}</div>
            <MyButton label="Default" size="lg"/>
          </div>
        </div>
        <div class="inline-buttons color">
          <div class="button">
            <div class="description">{{`<Button color=”default” />`}}</div>
            <MyButton label="Default" color="default"/>
          </div>
          <div class="button">
            <div class="description">{{`<Button color="primary" />`}}</div>
            <MyButton label="Default" color="primary"/>
          </div>
          <div class="button">
            <div class="description">{{`<Button color=”secondary” />`}}</div>
            <MyButton label="Default" color="secondary"/>
          </div>
          <div class="button">
            <div class="description">{{`<Button color=”danger” />`}}</div>
            <MyButton label="Default" color="danger"/>
          </div>
        </div>
        <div class="main-link">Icons: https://material.io/resources/icons/?style=round</div>
        <div class="main-bottom">created by <span style="font-weight: bold;">jnzm_02</span> - devChallenges.io</div>
      </div>
    </div> 
  </div>
</template>

<style scoped lang="scss">
#app {
  width: 100%;
  display: grid;
  grid-template-columns: 237px 1fr;
  background: white;
}

.left-bar {
  margin: 50px 50px 0;
  position: fixed;
  height: 100%;
  background-color: #FAFBFD;

  .top-word {
    cursor: pointer;
    font-size: 13px;
    color: #090F31;
    font-weight: bold;
    margin-bottom: 20px;
  }
  .options {
    margin-top: 122px;
    .option {
      cursor: pointer;
      width: 114px;
      color: #9E9E9E;
      font-size: 14px;
      margin-bottom: 25px;
    }
    .selected-option {
      color: #090F31;
      font-weight: bold;
    }
  }
}

.main {
  background-color: #FAFBFD;
  .main-body {
    margin: 50px 80px 0;
    .main-header {
      font-size: 24px;
      color: #090F31;
      font-weight: bold;
      margin-bottom: 50px;
    }
    .buttons {
      .description {
        margin-bottom: 12px;
        font-size: 14px;
        color: #090F31;
      }
    }
    .events {
      display: grid;
      grid-template-columns: 236px 236px;
      .description {
        margin-bottom: 12px;
        margin-top: 20px;
      }
    }
    .disabled {
      display: flex;
      .description {
        margin-bottom: 12px;
        margin-top: 50px;
      }
      gap: 50px;
    }
    .inline-buttons {
      display: flex;
      gap: 50px;
      .description {
        margin-bottom: 12px;
        font-size: 14px;
        color: #090F31;
        margin-top: 20px;
      }
    }
    .icons {
      .description {
        margin-bottom: 12px;
        margin-top: 50px;
      }
    }
    .size {
      .description {
        margin-bottom: 12px;
        margin-top: 50px;
      }
    }
    .color {
      .description {
        margin-bottom: 12px;
        margin-top: 50px;
      }
    }
    .color-effects {
      .description {
        margin-bottom: 12px;
        margin-top: 50px;
      }
    }
    .main-link {
      font-size: 14px;
      color: #828282;
      margin: 50px 0 34px;
    }
    .main-bottom {
      font-size: 14px;
      color: #A9A9A9;
      margin-bottom: 24px;
    }
  }
}
</style>
