<template>
  <div>
    
    <!--  -->
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
              <div class="btn btn-micro btn-info">수정</div>
              <div class="btn btn-micro btn-pale">취소</div>
              <div class="btn btn-micro btn-danger">삭제</div>
            </div>
          </div>
          <vuestic-modal :show.sync="show" v-bind:large="true" ref="largeModal"
                   :okText="'modal.confirm' | translate"
                   :cancelText="'modal.cancel' | translate">
            <div slot="title">{{'그룹원 초대' | translate}}</div>
            <div>

              <div class="form-group form-group-w-btn">
                <div class="input-group">
                  <input id="input-w-btn" required/>
                  <label class="control-label" for="input-w-btn">{{'email 주소를 입력해 주세요.'
                    | translate}}</label><i class="bar"></i>
                </div>
                <div class="btn btn-micro btn-primary">
                  {{'Add' | translate}}
                </div>
              </div>
              <div class="flex xs1"><div class="_green-rectangle"><div class="btn btn-micro btn-primary">
                  {{'Add' | translate}}
                </div></div></div>


            </div>
          </vuestic-modal>
        </vuestic-widget>
      </div>
    </div>
    <!-- 모달삽입 -->
    

    <div class="va-row">

    </div>

    <div class="va-row">
      <div class="flex md12 xs12">
        <vuestic-widget :headerText="$t('tables.styled')">
          <div class="table-responsive">
            <table class="table table-striped table-sm color-icon-label-table">
              <thead>
              <tr>
                <td></td>
                <td>{{'tables.headings.name' | translate}}</td>
                <td>{{'tables.headings.email' | translate}}</td>
                <td>{{'tables.headings.city' | translate}}</td>
                <td align="right">{{'tables.headings.score' | translate}}</td>
                <td align="middle"></td>
              </tr>
              </thead>
              <tbody>
              <tr>
                <td></td>
                <td>Matthew McCormick</td>
                <td>matthew30@mail.ol</td>
                <td>Vancouver</td>
                <td align="right">93</td>
                <td align="middle"></td>
              </tr>
              <tr>
                <td></td>
                <td>Nancy Bo</td>
                <td>nancy@boonweb.com</td>
                <td>Washington</td>
                <td align="right">280</td>
                <td align="middle"></td>
              </tr>
              <tr>
                <td></td>
                <td>Frederiko Lopez</td>
                <td>fr.lopez@webmail.sp</td>
                <td>Barcelona</td>
                <td align="right">16</td>
                <td align="middle"></td>
              </tr>
              <tr class="table-danger">
                <td>
                  <span class="badge badge-pill badge-danger">DANGER</span>
                </td>
                <td>Stanley Hummer</td>
                <td>mr_winner_2999@gmail.cb</td>
                <td>Manchester</td>
                <td align="right">57</td>
                <td align="middle">
                  <i
                    class="fa fa-exclamation-triangle icon-right input-icon error-icon"></i>
                </td>
              </tr>
              <tr class="table-success">
                <td>
                  <span class="badge badge-pill badge-primary">SUCCESS</span>
                </td>
                <td>Lendley Wintz</td>
                <td>9938198146@mailster.io</td>
                <td>Wien</td>
                <td align="right">113</td>
                <td align="middle" class="valid">
                  <i class="fa fa-check success-icon icon-right input-icon"></i>
                </td>
              </tr>
              <tr class="table-warning">
                <td>
                  <span class="badge badge-pill badge-warning">WARNING</span>
                </td>
                <td>Barbara Noz</td>
                <td>barbaranoz@mailster.io</td>
                <td>Brussels</td>
                <td align="right">68</td>
                <td align="middle"></td>
              </tr>
              <tr>
                <td></td>
                <td>Matthew McCormick</td>
                <td>matthew30@mail.ol</td>
                <td>Vancouver</td>
                <td align="right">93</td>
                <td align="middle"></td>
              </tr>
              <tr class="table-info">
                <td>
                  <span class="badge badge-pill badge-info">INFO</span>
                </td>
                <td>Nancy Bo</td>
                <td>nancy@boonweb.com</td>
                <td>Washington</td>
                <td align="right">280</td>
                <td align="middle"></td>
              </tr>
              </tbody>
            </table>
          </div>
        </vuestic-widget>
      </div>
    </div>

    

  </div>
</template>

<script>
import Vue from 'vue'
import BadgeColumn from './BadgeColumn.vue'
import FieldsDef
  from '../../vuestic-theme/vuestic-components/vuestic-datatable/data/fields-definition'
import ItemsPerPageDef
  from '../../vuestic-theme/vuestic-components/vuestic-datatable/data/items-per-page-definition'
import QueryParams from '../../vuestic-theme/vuestic-components/vuestic-datatable/data/query-params'
import { SpringSpinner } from 'epic-spinners'

import VaModal from '@/components/ui/modals/Modals.vue'
import Tags from '@/components/ui/tags/Tags.vue'
Vue.component('badge-column', BadgeColumn)

export default {
  name: 'Table',
  
  components: {
    SpringSpinner,
    VaModal
  },
  data () {
    return {
      apiUrl: 'https://vuetable.ratiw.net/api/users',
      apiMode: true,
      tableFields: FieldsDef.tableFields,
      itemsPerPage: ItemsPerPageDef.itemsPerPage,
      sortFunctions: FieldsDef.sortFunctions,
      paginationPath: '',
      defaultTablePerPage: 6,
      queryParams: QueryParams,
      show: true
    }
  },
  methods: {
    showGrmemListModal(){
      this.$refs.largeModal.open()
    }
  }
}
</script>

<style lang="scss">

.color-icon-label-table {
  td:first-child {
    width: 1rem;
  }
}
</style>
