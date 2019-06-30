<template>
<div>
    <!-- 목록보기 -->
    <div class="va-row">
        <div class="flex xs12 md12">
            <vuestic-widget :headerText="$t('Group List')">
            <div class="table-responsive">               
                <table class="table table-striped first-td-padding">
                <thead>
                <tr>
                    <td>group number</td>
                    <td>group name</td>
                    <td>group introduce</td>
                    <td align="right">
                    <button class="btn btn-info btn-micro" @click="showMediumModal()">
                        {{'group add' | translate}}
                    </button>
                    </td>                    
                </tr>
                </thead>
                <tbody>
                <tr>
                    <td>1</td>
                    <td>bit190603</td>
                    <td>비트캠프 서울시 뉴딜 일자리 자바스크립트 프레임워크 과정</td>
                    <td align="right">
                    <span >
                        <router-link to="/">
                        <button class="btn btn-primary btn-micro">view</button>
                        </router-link>
                    </span>
                    </td>                   
                </tr>
                <tr>
                    <td>2</td>
                    <td>project woon</td>
                    <td>스프링부트, 리액트, hibernate 사용한 협업프로그램 개발 </td>
                    <td align="right">
                    <span >
                        <button class="btn btn-primary btn-micro">view</button>                        
                    </span>
                    </td>                   
                </tr>
                <tr>
                    <td>3</td>
                    <td>festival WSDF</td>
                    <td>서울시 국제 스트릿 댄스 페스티발 개최 준비를 위한 화상 회의</td>
                    <td align="right">
                    <span >
                        <button class="btn btn-primary btn-micro">view</button>                       
                    </span>
                    </td>                    
                </tr>               
                <tr>
                    <td>5</td>
                    <td>bitcamp vues js study</td>
                    <td>비트캠프 종로 학원생 뷰 js 스터디 모임</td>
                    <td align="right">
                    <span >
                        <button class="btn btn-primary btn-micro">view</button>                        
                    </span>
                    </td>  
                </tr>
                </tbody>                    
                </table>
                <!-- 그룹 추가 버튼 클릭시 팝업 부분 -->                
                <vuestic-modal :show.sync="show" ref="mediumModal"
                    :okText="'modal.confirm' | translate"
                    :cancelText="'modal.cancel' | translate">
                
                <div slot="title">{{'Group Add' | translate}}</div>
                <div>
                    <h5>Group Name</h5>  
                </div>
                    <!-- 그룹명 -->
                <div class="form-group">
                <div class="input-group">
                    <input id="simple-input" required/>
                    <label class="control-label" for="simple-input">text</label><i class="bar"></i>
                </div>
                </div>
                
                <div>
                    <h5>Group Introduce</h5>  
                </div>
                    <!-- 그룹소개 -->
                <div class="form-group">
                    <div class="input-group">
                            <textarea type="text" id="simple-textarea" required></textarea>
                            <label class="control-label" for="simple-textarea">Textarea</label><i class="bar"></i>
                    </div>
                </div>
                </vuestic-modal>
            </div>           
            </vuestic-widget>
        </div>
    </div>

    <!-- 상세보기 페이지-->
    <div class="va-row">


        <div class="flex xs12 md12">
        <vuestic-widget :headerText="$t('Goup Detail')">
          <div class="table-responsive">
            <table class="table table-striped first-td-padding">
              
              <tbody>
              <tr>
                <td>Group name</td>
                <td>bit190603</td>
              </tr>
              <tr>
                <td>Group introduce</td>
                <td>비트캠프 서울시 뉴딜 일자리 자바스크립트 프레임워크 과정</td>
              </tr>
              <tr>
                <td>Group leader</td>
                <td>홍길동</td>
              </tr>
              <tr>
                <td>Group member list</td>
                <td>abc@bit.com, ee@bit.com, camp@bitcamp.com, gogo@bitcam.com</td>
              </tr>

              </tbody>
            </table>
            <div align="center">
              <div class="btn btn-micro btn-info">수정</div>
              <div class="btn btn-micro btn-danger">삭제</div>
            </div>
          </div>
        </vuestic-widget>
      </div>


    </div>
    
    <!-- 수정페이지(확인,취소,삭제 버튼) -->
    <div class="va-row">
      <div class="flex xs12 md12">
        <vuestic-widget :headerText="$t('Group Modify')">
          <div class="table-responsive">
            <table class="table table-striped first-td-padding">
              
              <tbody>
              <tr>
                <td>Group name</td>
                <td>
                  <div class="form-group">
                    <div class="input-group">
                      <input type="text" value="bit190603"/>
                      <i class="bar"></i>
                    </div>
                    </div>
                </td>
              </tr>
              <tr>
                <td>Group introduce</td>
                <td>
                  <div class="form-group">
                    <div class="input-group">
                          <textarea type="text" id="simple-textarea" >비트캠프 서울시 뉴딜 일자리 자바스크립트 프레임워크 과정</textarea>
                          <i class="bar"></i>
                    </div>
                  </div>

                </td>
              </tr>
              <tr>
                <td>Group leader</td>
                <td>홍길동</td>
              </tr>
              <tr>
                <td>Group member list</td>
                <td>abc@bit.com, ee@bit.com, camp@bitcamp.com, gogo@bitcam.com
                  <!-- 그룹원 수정 버튼 클릭시 팝업 -->
                  <div class="btn btn-micro btn-primary" @click="showGrmemListModal()">수정</div>
                </td>
              </tr>

              </tbody>
            </table>
            <div align="center">
              <div class="btn btn-micro btn-info">확인</div>
              <div class="btn btn-micro btn-pale">취소</div>
              <div class="btn btn-micro btn-danger">삭제</div>
            </div>
          </div>
          <!-- 그룹원 수정 버튼 클릭시 팝업 내용 -->
          <vuestic-modal :show.sync="show" v-bind:large="true" ref="largeModal"
                   :okText="'modal.confirm' | translate"
                   :cancelText="'modal.cancel' | translate">
            <div slot="title">{{'그룹원 초대' | translate}}</div>
            <div>

              <div class="form-group form-group-w-btn">
                <div class="input-group">
                  <input id="input-w-btn" required/>
                  <label class="control-label" for="input-w-btn">email 주소를 입력해 주세요.</label><i class="bar"></i>
                </div>
                <div class="btn btn-micro btn-primary">
                  {{'Add' | translate}}
                </div>
              </div>
              <div class="flex xs1"><div class="_green-rectangle"></div></div>


            </div>
          </vuestic-modal>
        </vuestic-widget>
      </div>
    </div>
     
    
    
  

</div>
    
</template>
<script>
import VaModal from '@/components/ui/modals/Modals.vue'
export default {
  name: 'modals',
  components: {
    VaModal
  },
  data () {
    return {
      show: true,
    }
  },
  methods: {
    showMediumModal () {
      this.$refs.mediumModal.open()
    },
    showGrmemListModal(){
      this.$refs.largeModal.open()
    }
  }
}
</script>
<style scoped>

</style>