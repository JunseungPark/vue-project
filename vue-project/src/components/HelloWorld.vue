<template>
  <div>
    <div class="b-example-divider"></div>
    <div class="modal modal-tour position-static d-block bg-secondary py-5" tabindex="-1" role="dialog" id="modalTour">
      <div class="modal-dialog" role="document">
        <div class="modal-content rounded-4 shadow">
          <div class="modal-body p-5">

            <h2 class="fw-bold mb-3">인라인 이벤트</h2>
            <button class="btn btn-lg btn-primary" v-on:click="good1+=1">Great, thanks!</button>
            <button class="btn btn-lg btn-primary" type="button" @click="good1+=1">Great, thanks!</button>
            <h2 class="fw-bold mb-0">Vaule: {{good1}}</h2>

          </div>
        </div>
      </div>
    </div>
    <div class="b-example-divider"></div>
    <div class="modal modal-tour position-static d-block bg-secondary py-5" tabindex="-1" role="dialog" id="modalTour">
      <div class="modal-dialog" role="document">
        <div class="modal-content rounded-4 shadow">
          <div class="modal-body p-5">

            <h2 class="fw-bold mb-3">이벤트 핸들링 메서드</h2>
            <button class="btn btn-lg btn-primary" type="button" v-on:click="clickGood()">Great, thanks!</button>
            <button class="btn btn-lg btn-primary" type="button" @click="clickGood()">Great, thanks!</button>
            <h2 class="fw-bold mb-0">Vaule: {{good2}}</h2>

          </div>
        </div>
      </div>
    </div>
    <div class="b-example-divider"></div>

    <div class="modal modal-tour position-static d-block bg-secondary py-5" tabindex="-1" role="dialog" id="modalTour">
      <div class="modal-dialog" role="document">
        <div class="modal-content rounded-4 shadow">
          <div class="modal-body p-5">

            <h2 class="fw-bold mb-3">예금/인출</h2>
            <p>
            <input tpye="text" v-model="amount" class="form-control" /></p>
            <p>
                <button id="deposit" v-on:click="deposit" class="btn btn-primary">예금</button>
                <button id="deposit" v-on:click="withdraw" class="btn btn-primary">인출</button>
            </p>
            <h3>계좌 잔고 : {{balance}}</h3>

          </div>
        </div>
      </div>
    </div>
    <div class="b-example-divider"></div>
    <div class="modal modal-tour position-static d-block bg-secondary py-5" tabindex="-1" role="dialog" id="modalTour">
      <div class="modal-dialog" role="document">
        <div class="modal-content rounded-4 shadow">
          <div class="modal-body p-5">

            <h2 class="fw-bold mb-3">이벤트 수식어(Stop)</h2>
            <button type="button" class="div1" @click="func1">
              상단
              <button type="button" class="div2" @click.stop="func2">
                중단
                <button type="button" class="div2" @click="func3">
                  하단
                </button>
              </button>
            </button>
          </div>
        </div>
      </div>
    </div>
    <div class="b-example-divider"></div>

    <div class="modal modal-tour position-static d-block bg-secondary py-5" tabindex="-1" role="dialog" id="modalTour">
      <div class="modal-dialog" role="document">
        <div class="modal-content rounded-4 shadow">
          <div class="modal-body p-5">

            <h2 class="fw-bold mb-3">이벤트 수식어(Prevent)</h2>
              <!-- [a 태그 : 일반 네이버 링크 이동 수행] -->
              <a class="btn btn-primary" href="https://www.naver.com" target="_blank">이벤트 정상 수행</a>

              <hr>

              <!-- [a 태그 : click 이벤트 prevent 막기] -->
              <a class="btn btn-primary" href="https://www.naver.com" target="_blank" @click.prevent=''>이벤트 방지</a>
          </div>
        </div>
      </div>
    </div>
    <div class="b-example-divider"></div>

    <div class="modal modal-tour position-static d-block bg-secondary py-5" tabindex="-1" role="dialog" id="modalTour">
      <div class="modal-dialog" role="document">
        <div class="modal-content rounded-4 shadow">
          <div class="modal-body p-5">

            <h2 class="fw-bold mb-3">이벤트 수식어(capture)</h2>
            <button type="button" class="div1" @click.capture="func1">
              상단
              <button type="button" class="div2" @click="func2">
                중단
                <button type="button" class="div2" @click="func3">
                  하단
                </button>
              </button>
            </button>

          </div>
        </div>
      </div>
    </div>
    <div class="b-example-divider"></div>

    <div class="modal modal-tour position-static d-block bg-secondary py-5" tabindex="-1" role="dialog" id="modalTour">
      <div class="modal-dialog" role="document">
        <div class="modal-content rounded-4 shadow">
          <div class="modal-body p-5">

            <h2 class="fw-bold mb-3">이벤트 수식어(self)</h2>
            <button type="button" class="div1" @click="func1">
              상단
              <button type="button" class="div2" @click.self="func2">
                중단
                <button type="button" class="div2" @click="func3">
                  하단
                </button>
              </button>
            </button>

          </div>
        </div>
      </div>
    </div>
    <div class="b-example-divider"></div>

    <div class="modal modal-tour position-static d-block bg-secondary py-5" tabindex="-1" role="dialog" id="modalTour">
      <div class="modal-dialog" role="document">
        <div class="modal-content rounded-4 shadow">
          <div class="modal-body p-5">

            <h2 class="fw-bold mb-3">키 이벤트</h2>
            <div class="col-12">
              <label for="address" class="form-label">Keyup</label>
              <input type="text" class="form-control" @keyup="printEvent('keyup')" v-model="name1"/>
            </div>
            <div class="col-12">
              <label for="address" class="form-label">Keydown</label>
              <input type="text" class="form-control" @keydown="printEvent('keydown')" v-model="name2"/>
            </div>
            <div class="col-12">
              <label for="address" class="form-label">enter</label>
              <input type="text" class="form-control" @keyup.enter="printEvent('enter')" v-model="name4"/>
            </div>
            <div class="col-12">
              <label for="address" class="form-label">space</label>
              <input type="text" class="form-control" @keyup.space="printEvent('space')" v-model="name5"/>
            </div>
            <div class="col-12">
              <label for="address" class="form-label">left</label>
              <input type="text" class="form-control" @keyup.left="printEvent('left')" v-model="name6"/>
            </div>

            <div class="col-12">
              <label for="address" class="form-label">altKey</label>
              <input type="text" class="form-control" @keyup.18="printEvent('altKey')" v-model="name7"/>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="b-example-divider"></div>

    <div class="modal modal-tour position-static d-block bg-secondary py-5" tabindex="-1" role="dialog" id="modalTour">
      <div class="modal-dialog" role="document">
        <div class="modal-content rounded-4 shadow">
          <div class="modal-body p-5">

            <h2 class="fw-bold mb-3">마우스 이벤트</h2>

            <div class="right_container bg-black" @click="mouseClick($event)" >
              <img class="mouse-img" width="200px" src="../assets/mokey.jpg" :style="{left:xPosition, top:yPosition}"/>
            </div>

            <h2 class="fw-bold mb-0">clientX: {{clientX}}</h2>
            <h2 class="fw-bold mb-0">clientY: {{clientY}}</h2>
            <h2 class="fw-bold mb-0">pageX: {{pageX}}</h2>
            <h2 class="fw-bold mb-0">pageY: {{pageY}}</h2>
            <h2 class="fw-bold mb-0">screenX: {{screenX}}</h2>
            <h2 class="fw-bold mb-0">screenY: {{screenY}}</h2>
          </div>
        </div>
      </div>
    </div>
    <div class="b-example-divider"></div>

    <div class="modal modal-tour position-static d-block bg-secondary py-5" tabindex="-1" role="dialog" id="modalTour">
      <div class="modal-dialog" role="document">
        <div class="modal-content rounded-4 shadow">
          <div class="modal-body p-5">

            <h2 class="fw-bold mb-3">스타일 바인딩</h2>
            <div :style="{color: activeColor, fontSize: fontSize + 'px'}">스타일바인딩 (단일 객체형)</div>
            <div :style="styleObject">스타일바인딩 (복수)</div>
            <div class="mb-5" v-bind:style="[baseStyles, overridingStyles]">배열 스타일바인딩</div>
            <div style="
              -webkit-transform: rotate(45deg);
              -moz-transform: rotate(45deg);
              -ms-transform: rotate(45deg);
              -o-transform: rotate(45deg);
              transform: rotate(45deg);">밴더 프릭스</div>
          </div>
        </div>
      </div>
    </div>
    <div class="b-example-divider"></div>

    <div class="modal modal-tour position-static d-block bg-secondary py-5" tabindex="-1" role="dialog" id="modalTour">
      <div class="modal-dialog" role="document">
        <div class="modal-content rounded-4 shadow">
          <div class="modal-body p-5">

            <h2 class="fw-bold mb-3">이미지 옮기기</h2>
            <div style="width:400px" id="Example" v-on:contextmenu.prevent="ctxStop" @mouseup.left="leftMouse()" @mouseup.right="rightMouse()">
                <div>
                    Left Click : 왼쪽으로<br>
                    Right Click : 오른쪽으로
                </div>
                <img src="../assets/mokey-removebg-preview.png" width="100px" v-bind:style="{ position:'absolute', left: pos.left + 'px',
                top:pos.top +'px' }" />

            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="b-example-divider"></div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      good1: 0,
      good2: 0,
      name1: 'keyup',
      name2: 'keydown',
      name3: 'keypress',
      name4: 'enter',
      name5: 'space',
      name6: 'left',
      name7: '',
      balance: 0,
      amount: 0,
      xPosition: 10,
      yPosition: 10,
      clientX: 0,
      clientY: 0,
      pageX: 0,
      pageY: 0,
      screenX: 0,
      screenY: 0,
      activeColor: 'red',
      fontSize: 30,

      styleObject: {
        color: 'blue',
        fontSize: '40px'
      },

      baseStyles: {
        color: 'green',
        fontSize: '30px'
      },
      overridingStyles: {
        fontWeight: 700,
        fontStyle: 'italic'
        // fontStyle: 'normal'
      },

      pos: {
        left: 100,
        top: 100
      }
    }
  },
  methods: {
    clickGood() {
      if (this.good2 <= 10) this.good2++
      else this.good2--
    },
    func1() {
      alert('상단클릭됨')
    },
    func2() {
      alert('중단클릭됨')
    },
    func3() {
      alert('하단클릭됨')
    },
    printEvent(val) {
      alert(val)
    },

    mouseClick(event) {
      this.clientX = event.clientX
      this.clientY = event.clientY
      this.pageX = event.pageX
      this.pageY = event.pageY
      this.screenX = event.screenX
      this.screenY = event.screenY
    },

    deposit() {
      var amt = parseInt(this.amount)
      if (amt <= 0) {
        alert('0보다 큰 값을 예금해야한다. ')
      } else {
        this.balance += amt
      }
    },
    withdraw() {
      var amt = parseInt(this.amount)
      if (amt <= 0) {
        alert('0보다 큰 값을 인출할 수 있다. ')
      } else if (amt > this.balance) {
        alert('잔고보다 많은 금액을 인출할 수 있다. ')
      } else {
        this.balance -= amt
      }
    },

    leftMouse() {
      if (this.pos.left > 30) this.pos.left -= 30
    },
    rightMouse() {
      this.pos.left += 30
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  div {
    font-family: 'GmarketSansMedium';
  }

  .b-example-divider {
      height: 3rem;
      background-color: rgba(0, 0, 0, .1);
      border: solid rgba(0, 0, 0, .15);
      border-width: 1px 0;
      box-shadow: inset 0 0.5em 1.5em rgb(0 0 0 / 10%), inset 0 0.125em 0.5em rgb(0 0 0 / 15%);
  }

  @font-face {
      font-family: 'GmarketSansMedium';
      src: url('https://cdn.jsdelivr.net/gh/projectnoonnu/noonfonts_2001@1.1/GmarketSansMedium.woff') format('woff');
      font-weight: normal;
      font-style: normal;
  }
</style>
