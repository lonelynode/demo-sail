<template>
  <f7-page id="sail" style="background: white;">
    <f7-navbar class="navbar-theme" style="background: white;">
      <f7-nav-left>
        <f7-link panel-open="left">Back</f7-link>
      </f7-nav-left>
      <f7-nav-title>Test Sail</f7-nav-title>
      <f7-nav-right>
        <f7-link panel-open="right">Save</f7-link>
      </f7-nav-right>
    </f7-navbar>
    <f7-toolbar tabbar :position="'bottom'">
      <f7-link tab-link="#tab-2">home</f7-link>
    </f7-toolbar>
    <div class="subnavbar" style="width: 100%; background: #ffffff;">
      <div class="subnavbar-inner navbar-theme">
        <div class="segmented subnavbar-border" style="border: solid 1px purple;">
          <button href="#opportunity_detail_NewOppGen" class="button gen" @click="itemClick('gen')" style="line-height: 2rem; height: 2rem;">
            General
          </button>
          <button href="#opportunity_detail_NewOppCus" class="button button-active scope" @click="itemClick('scope')" style="line-height: 2rem; height: 2rem;">
            Scope
          </button>
          <button href="#opportunity_detail_NewOppRem" class="button remarks" @click="itemClick('remarks')" style="line-height: 2rem; height: 2rem;">Remarks
          </button>
          <button href="#opportunity_detail_NewOppINT" class="button int" @click="itemClick('int')" style="line-height: 2rem; height: 2rem;">Interaction
          </button>
        </div>
      </div>
    </div>


    <div class="display-content" style="margin-top: 10px; padding-top: 12px;">
      <div id="opportunity_detail_NewOppGen" style="display: none" class="generalDiv">
        <div class="list">
          <div class="item-content item-input">
            <div class="item-inner">
              <div class="item-title item-label input-title">
                <span class="">Carrier:</span>
                <span class="asterisk">*</span>
              </div>
              <div class="item-input-wrap">
                <select>
                  <option :value="carrierInfo.code" v-for="(carrierInfo, index) in carrierList" :key="carrierInfo.code">{{ carrierInfo.value }}</option>
                </select>
              </div>
            </div>
          </div>
          <div class="item-content item-input">
            <div class="item-inner">
              <div class="item-title item-label input-title">
                <span>Sales:</span>
                <span class="asterisk">*</span>
              </div>
              <div class="item-input-wrap">
                <input type="text" v-model="sail" @click="popupOpened = true">
                <span class="input-clear-button"></span>
              </div>
            </div>
          </div>
          <div class="item-content item-input">
            <div class="row" style="width: 100%;">
              <div class="col-65">
                <div class="item-inner">
                  <div class="item-title item-label input-title">
                    <span>Customer:</span>
                    <span class="asterisk">*</span>
                  </div>
                  <div class="item-input-wrap">
                    <input type="text" v-model="customer">
                  </div>
                </div>
              </div>
              <div class="col-35">
                <div class="item-inner">
                  <div class="item-title item-label input-title">
                    <span>&nbsp;</span>
                  </div>
                  <div class="item-input-wrap">
                    <input type="text" v-model="leadTrade">
                    <span class="input-clear-button"></span>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="row" style="width: 100%;">
            <div class="col-45">
              <div class="item-content item-input">
                <div class="item-inner">
                  <div class="item-title item-label input-title">
                    <span>Lead Trade:</span>
                  </div>
                  <div class="item-input-wrap">
                    <input type="text" v-model="leadTrade">
                    <span class="input-clear-button"></span>
                  </div>
                </div>
              </div>
            </div>

            <div class="col-45">

              <div class="item-content item-input">
                <div class="item-inner">
                  <div class="item-title item-label input-title">
                    <span>Lead Bound:</span>
                  </div>
                  <div class="item-input-wrap">
                    <input type="text" v-model="leadBouond">
                    <span class="input-clear-button"></span>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="item-content item-input">
            <div class="item-inner">
              <div class="item-title item-label input-title">
                <span>Customer Area:</span>
              </div>
              <div class="item-input-wrap">
                <input type="text" v-model="customerArea">
                <span class="input-clear-button"></span>
              </div>
            </div>
          </div>
          <div class="item-content item-input">
            <div class="item-inner">
              <div class="item-title item-label input-title">
                <span>Contact Person:</span>
              </div>
              <div class="item-input-wrap">
                <input type="text" v-model="contactPerson">
                <span class="input-clear-button"></span>
              </div>
            </div>
          </div>
          <div id="tpt">

            <label class="item-checkbox item-content">
              <input type="checkbox" name="demo-checkbox" value="Books" v-model="isTPTUser"/>
              <i class="icon icon-checkbox"></i>
              <div class="item-inner">
                <div class="item-title">TPT EB ISC</div>
              </div>
            </label>
          </div>
          <div class="item-content item-input" style="margin-top: 10px;" v-show="isTPTUser">
            <div class="item-inner">
              <div class="item-title item-label input-title">
                <span>Year:</span>
                <span class="asterisk">*</span>
              </div>
              <div class="item-input-wrap">
                <input type="text" v-model="customer">
                <span class="input-clear-button"></span>
              </div>
            </div>
          </div>
          <button class="button send-email">Send Email</button>
        </div>

      </div>
      <div id="opportunity_detail_NewOppCus" class="ScopeDiv">
        <div class="list">
          <div class="item-content item-input">
            <div class="item-inner">
              <div class="item-title item-label input-title">
                <span class="">Carrier:</span>
                <span class="asterisk">*</span>
              </div>
              <div class="item-input-wrap">
                <select>
                  <option :value="carrierInfo.code" v-for="(carrierInfo, index) in carrierList" :key="carrierInfo.code">{{ carrierInfo.value }}</option>
                </select>
              </div>
            </div>
          </div>
          <div class="scope-block">
            <div class="item-content item-input">
              <div class="item-inner gridHeader">
                <div class="item-title item-label">
                  <span class="" style="float: left; margin-right: 5px;">Opportunity Scope</span>
                  <hr>
                </div>
              </div>
            </div>
            <div class="row" style="padding: 0 30px;">
              <div class="col scope-field">
                <div class="row" style="width: 100%; padding: 8px 0;">
                  <div class="row">
                    <div class="input-title">
                      <span>Target Period:</span>
                      <span class="asterisk">*</span>
                    </div>
                  </div>

                  <div class="row">
                    <div class="col-40">
                      <!--<div class="item-content item-input">-->
                      <div class="item-input">
                        <div class="item-inner">
                          <div class="item-input-wrap">
                            <input type="text" @click="openPicker3" id="period-from-date">
                            <span class="input-clear-button"></span>
                          </div>
                        </div>
                      </div>
                    </div>
                    <div class="col-15">
                      <div class="item-input">
                        <div class="item-inner">
                          <div data-v-50803bf8="" class="item-title item-label input-title">
                            <span data-v-50803bf8="">to</span>
                          </div>
                        </div>
                      </div>
                    </div>
                    <div class="col-40">
                      <div class="item-input">
                        <div class="item-inner">
                          <div class="item-input-wrap">
                            <input type="text" @click="openPicker2" id="demo-picker-device">
                            <span class="input-clear-button"></span>
                          </div>
                        </div>
                      </div>
                    </div>

                  </div>


                </div>
                <div class="row" style="width: 100%; padding: 8px 0;">
                  <div class="row">
                    <div class="item-title item-label input-title">
                      <span>Cargo Group</span>
                      <span class="asterisk">*</span>
                      <span>/Nature:</span>
                    </div>
                  </div>

                  <div class="row" style="width: 100%;">
                    <div class="col-40">
                      <div class="item-input">
                        <div class="item-inner">
                          <div class="item-input-wrap">
                            <select>
                              <option :value="tradeInfo.code" v-for="(tradeInfo, index) in tradeList" :key="tradeInfo.code">{{ tradeInfo.value }}</option>
                            </select>
                          </div>
                        </div>
                      </div>
                    </div>
                    <div class="col-40">
                      <div class="item-input">
                        <div class="item-inner">
                          <div class="item-input-wrap">
                            <select>
                              <option :value="tradeInfo.code" v-for="(tradeInfo, index) in tradeList" :key="tradeInfo.code">{{ tradeInfo.value }}</option>
                            </select>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>


                </div>
                <div class="row" style="width: 100%; padding: 8px 0;">
                  <div class="row" style="width: 100%">
                    <div class="item-title item-label input-title">
                      <span>Biz Nature</span>
                      <span class="asterisk">*</span>
                    </div>
                  </div>
                  <div class="row" style="width: 100%">
                    <div class="item-input-wrap">
                      <select>
                        <option>Open</option>
                        <option>Committee</option>
                      </select>
                    </div>
                  </div>

                </div>


              </div>
              <div class="col scope-field">

                <div class="row" style="width: 100%; padding: 8px 0;">
                  <div class="row" style="width: 100%;">
                    <div class="item-title item-label input-title">
                      <span>Trade</span>
                      <span class="asterisk">*</span>
                      <span>/Lane/Bound:</span>
                    </div>
                  </div>

                  <div class="row" style="width: 100%;">
                    <div class="col-30">
                      <div class="item-input">
                        <div class="item-inner">
                          <div class="item-input-wrap">
                            <select @change="addTradeArray">
                              <option :value="tradeInfo.code" v-for="(tradeInfo, index) in tradeList" :key="tradeInfo.code">{{ tradeInfo.value }}</option>
                            </select>
                          </div>
                        </div>
                      </div>
                    </div>
                    <div class="col-30">
                      <div class="item-input">
                        <div class="item-inner">
                          <div class="item-input">
                            <div class="item-input-wrap">
                              <input type="text" value="Any" readonly>
                              <!--<span>Any</span>-->
                            </div>
                          </div>
                        </div>
                      </div>
                    </div>
                    <div class="col-30">
                      <div class="item-input">
                        <div class="item-inner">
                          <div class="item-input">
                            <div class="item-input-wrap">
                              <input type="text" value="Any" readonly>
                            </div>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>

                </div>

                <div class="row" style="width: 100%; padding: 8px 0;" v-for="(trade, index) in tradeArray">
                  <div class="col-30">
                    <div class="item-input">
                      <div class="item-inner">
                        <div class="item-input-wrap">
                          <select v-model="trade.trade">
                            <option :value="tradeInfo.code" v-for="tradeInfo in tradeList" :key="tradeInfo.code">{{ tradeInfo.value }}</option>
                          </select>
                        </div>
                      </div>
                    </div>
                  </div>
                  <div class="col-30">
                    <div class="item-input">
                      <div class="item-inner">
                        <div class="item-input-wrap">
                          <select>
                            <option :value="tradeInfo.code" v-for="(tradeInfo, index) in tradeList" :key="tradeInfo.code">{{ tradeInfo.value }}</option>
                          </select>
                        </div>
                      </div>
                    </div>
                  </div>
                  <div class="col-30">
                    <div class="item-input">
                      <div class="item-inner">
                        <div class="item-input-wrap">
                          <select>
                            <option :value="tradeInfo.code" v-for="(tradeInfo, index) in tradeList" :key="tradeInfo.code">{{ tradeInfo.value }}</option>
                          </select>
                        </div>
                      </div>
                    </div>
                  </div>
                  <div class="col-5" @click="delTradeInfo(index)">del</div>


                </div>

              </div>
            </div>
          </div>
          <div class="scope-block">
            <div class="item-content item-input">
              <div class="item-inner gridHeader">
                <div class="item-title item-label">
                  <span class="" style="float: left; margin-right: 5px;">Details</span>
                  <hr>
                </div>
              </div>
            </div>
            <div class="row" style="padding: 0 30px;">
              <div class="col scope-field">
                <div class="row" style="width: 100%; padding: 8px 0;">
                  <div class="row">
                    <div class="item-title item-label input-title">
                      <span>Status</span>
                      <span class="asterisk">*</span>
                    </div>
                  </div>
                  <div class="row">
                    <div class="col">
                      <div class="item-input">
                        <div class="item-input-wrap">
                          <select>
                            <option>Validate</option>
                            <option>Reject</option>
                            <option>Failed</option>
                          </select>
                        </div>
                      </div>
                    </div>
                  </div>

                </div>

              </div>
              <div class="col scope-field">
                <div class="row" style="width: 100%; padding: 8px 0;">
                  <div class="row">
                    <div class="item-title item-label input-title">
                      <span>Likelihood of Success:</span>
                      <span class="asterisk">*</span>
                    </div>
                  </div>

                  <div class="row">
                    <div class="col">
                      <div class="item-input-wrap">
                        <select>
                          <option>High</option>
                          <option>Medium</option>
                          <option>Low</option>
                        </select>
                      </div>
                    </div>
                  </div>

                </div>

              </div>
              <div class="col scope-field">
                <div class="row" style="width: 100%; padding: 8px 0;">
                  <div class="row">
                    <div class="item-title item-label input-title">
                      <span>Critial Success Factor:</span>
                    </div>
                  </div>

                  <div class="row">
                    <div class="col">
                      <div class="item-input-wrap">
                        <input type="text">
                        <span class="input-clear-button"></span>
                      </div>
                    </div>
                  </div>

                </div>

              </div>
            </div>
            <div class="row" style="padding: 0 30px;">
              <div class="col scope-field">
                <div class="row" style="width: 100%; padding: 8px 0;">
                    <div class="row">
                      <div class="item-title item-label input-title">
                        <span>Expected Vol:</span>
                      </div>
                    </div>

                    <div class="row">
                      <div class="col">
                        <div class="item-input-wrap">
                          <input type="text">
                          <span class="input-clear-button"></span>
                        </div>
                      </div>
                    </div>
                </div>

              </div>
              <div class="col scope-field">
                <div class="row" style="width: 100%; padding: 8px 0;">
                    <div class="row">
                      <div class="item-title item-label input-title">
                        <span>Target MQC:</span>
                      </div>
                    </div>

                    <div class="row">
                      <div class="col">
                        <div class="item-input-wrap">
                          <input type="text">
                          <span class="input-clear-button"></span>
                        </div>
                      </div>
                    </div>
                </div>

              </div>
              <div class="col scope-field">
                <div class="row" style="width: 100%; padding: 8px 0;">
                    <div class="row">
                      <div class="item-title item-label input-title">
                        <span>Customer Total Annual Vol.(All carriers):</span>
                      </div>
                    </div>

                    <div class="row">
                      <div class="col-70">
                        <div class="item-input-wrap">
                          <input type="text">
                          <span class="input-clear-button"></span>
                        </div>
                      </div>
                      <div class="col-25">
                        <div class="item-input-wrap">
                          <select >
                            <option>TEU/week</option>
                            <option>TEU</option>
                            <option>Total TEU</option>
                          </select>
                        </div>
                      </div>
                    </div>
                </div>

              </div>
            </div>
          </div>
          <div class="scope-block">
            <div class="item-content item-input">
              <div class="item-inner gridHeader">
                <div class="item-title item-label">
                  <span class="" style="float: left; margin-right: 5px;">Agreement/Contract</span>
                  <hr>
                </div>
              </div>
            </div>
            <div class="row" style="padding: 0 30px;">
              <div class="col scope-field">
                <div class="row" style="width: 100%; padding: 8px 0;">
                    <div class="row">
                      <div class="item-title item-label input-title">
                        <span>Bid Required:</span>
                      </div>
                    </div>

                    <div class="row">
                      <div class="col">
                        <div class="item-input-wrap">
                          <input type="text">
                          <span class="input-clear-button"></span>
                        </div>
                      </div>
                    </div>

                </div>

              </div>
              <div class="col scope-field">
                <div class="row" style="width: 100%; padding: 8px 0;">
                    <div class="row">
                      <div class="item-title item-label input-title">
                        <span>Competitors:</span>
                      </div>
                    </div>

                    <div class="row">
                      <div class="col">
                        <div class="item-input-wrap">
                          <textarea></textarea>
                        </div>
                      </div>
                    </div>

                </div>

              </div>
              <div class="col scope-field">
                <div class="row" style="width: 100%; padding: 8px 0;">
                    <div class="row">
                      <div class="item-title item-label input-title">
                        <span>New Signed Contract/Agreement#:</span>
                      </div>
                    </div>

                    <div class="row">
                      <div class="col">
                        <div class="item-input-wrap">
                          <input type="text">
                          <span class="input-clear-button"></span>
                        </div>
                      </div>
                    </div>

                </div>

              </div>
              <div class="col scope-field">
                <div class="row" style="width: 100%; padding: 8px 0;">
                    <div class="row">
                      <div class="item-title item-label input-title">
                        <span>New Signed Contact/Agreement's Effective Period:</span>
                      </div>
                    </div>

                    <div class="row">
                      <div class="col">
                        <div class="item-input-wrap">
                          <input type="text">
                          <span class="input-clear-button"></span>
                        </div>
                      </div>
                    </div>

                </div>

              </div>
              <div class="col scope-field">
                <div class="row" style="width: 100%; padding: 8px 0;">
                    <div class="row">
                      <div class="item-title item-label input-title">
                        <span>New Signed Contract/Agreement's MQC:</span>
                      </div>
                    </div>

                    <div class="row">
                      <div class="col">
                        <div class="item-input-wrap">
                          <input type="text">
                          <span class="input-clear-button"></span>
                        </div>
                      </div>
                    </div>
                </div>

              </div>
            </div>
          </div>
          <div class="scope-block">
            <div class="item-content item-input">
              <div class="item-inner gridHeader">
                <div class="item-title item-label">
                  <span class="" style="float: left; margin-right: 5px;">References</span>
                  <hr>
                </div>
              </div>
            </div>
            <div class="row" style="padding: 0 30px;">
              <div class="col scope-field">

                <div class="row" style="width: 100%; padding: 8px 0;">

                    <ul style="width: 100%; padding: 0;">
                      <li style="padding: 0;" class="item-content item-input">
                        <div class="item-inner">
                          <div class="item-title item-label input-title">
                            <span>Services:</span>
                          </div>
                          <div class="item-input-wrap">
                            <input id="autocomplete-dropdown" type="text" placeholder="Fruit">
                            <span class="input-clear-button"></span>
                          </div>
                        </div>
                      </li>
                    </ul>

                    <div class="row">
                      <div class="col-30">
                        <div class="item-input-wrap">
                          <input type="text">
                          <span class="input-clear-button"></span>
                        </div>
                      </div>
                      <div class="col-30">
                        <div class="item-input-wrap">
                          <input type="text">
                          <span class="input-clear-button"></span>
                        </div>
                      </div>
                      <div class="col-30">
                        <div class="item-input-wrap">
                          <input type="text">
                          <span class="input-clear-button"></span>
                        </div>
                      </div>

                    </div>



                </div>
                <div class="row" style="width: 100%; padding: 8px 0;">

                    <div class="row">
                      <div class="col-30">
                        <div class="item-input-wrap">
                          <input type="text">
                          <span class="input-clear-button"></span>
                        </div>
                      </div>
                      <div class="col-30">
                        <div class="item-input-wrap">
                          <input type="text">
                          <span class="input-clear-button"></span>
                        </div>
                      </div>
                      <div class="col-30">
                        <div class="item-input-wrap">
                          <input type="text">
                          <span class="input-clear-button"></span>
                        </div>
                      </div>

                    </div>
                </div>
              </div>
              <div class="col scope-field">

                <div class="row" style="width: 100%; padding: 8px 0;">
                    <div class="row">
                      <div class="item-title item-label input-title">
                        <span>Total TPP Volume:</span>
                      </div>
                    </div>

                    <div class="row">
                      <div class="col-75">
                        <div class="item-input-wrap">
                          <input type="text">
                          <span class="input-clear-button"></span>
                        </div>
                      </div>
                      <div class="col-20">
                        <div class="item-input-wrap">
                          <input type="text" value="Any">
                        </div>
                      </div>

                    </div>
                </div>
                <div class="row" style="width: 100%; padding: 8px 0;">
                    <div class="row">
                      <div class="item-title item-label input-title">
                        <span>Total TPP Volume:</span>
                      </div>
                    </div>

                    <div class="row">
                      <div class="col-75">
                        <div class="item-input-wrap">
                          <input type="text" @click="openPicker3">
                          <span class="input-clear-button"></span>
                        </div>
                      </div>
                      <div class="col-20">
                        <div class="item-input-wrap">
                          <input type="text" value="TEU">
                        </div>
                      </div>

                    </div>

                </div>
                <div class="row" style="width: 100%; padding: 8px 0;">
                    <div class="row">
                      <div class="item-title item-label input-title">
                        <span>Commodity</span>
                      </div>
                    </div>

                    <div class="row">
                      <div class="col">
                        <div class="item-input-wrap">
                          <textarea></textarea>
                        </div>
                      </div>
                    </div>

                </div>
                <div class="row" style="width: 100%; padding: 8px 0;">
                    <div class="row">
                      <div class="item-title item-label input-title">
                        <span>Size/Type:</span>
                      </div>
                    </div>

                    <div class="row">
                      <div class="col">
                        <div class="item-input-wrap">
                          <select @change="addSizeArray">
                            <option v-for="item in sizeTypeList">{{ item }}</option>
                          </select>
                        </div>
                      </div>
                    </div>
                </div>
                <div class="row"v-for="(sizeTypeInfo, index) in sizeTypeArray" style="width: 100%; padding: 8px 0;">
                  <div class="col-85">
                    <div class="item-input">
                      <div class="item-inner">
                        <div class="item-input-wrap">
                          <select>
                            <option v-for="item in sizeTypeList">{{ item }}</option>
                          </select>
                        </div>
                      </div>
                    </div>
                  </div>
                  <div class="col-5" @click="delSizeType(index)">del</div>
                </div>

              </div>
            </div>
          </div>
        </div>
      </div>

      <div id="opportunity_detail_NewOppRem" class="RemarkseDiv" style="display: none">
        <div class="list">
          <ul>
            <li class="item-content item-input">
              <div class="item-inner">
                <div class="item-title item-label input-title">
                  <span class="">Carrier:</span>
                  <span class="asterisk">*</span>
                </div>
                <div class="item-input-wrap">
                  <select>
                    <option :value="carrierInfo.code" v-for="(carrierInfo, index) in carrierList" :key="carrierInfo.code">{{ carrierInfo.value }}</option>
                  </select>
                </div>
              </div>
            </li>
            <li class="item-content item-input">
              <div class="item-inner">
                <div class="item-title item-label input-title">
                  <span>Customer Service:</span>
                </div>
                <div class="item-input-wrap">
                  <textarea></textarea>
                  <span class="input-clear-button"></span>
                </div>
              </div>
            </li>
            <li class="item-content item-input">
              <div class="item-inner">
                <div class="item-title item-label input-title">
                  <span>Operation:</span>
                </div>
                <div class="item-input-wrap">
                  <textarea></textarea>
                  <span class="input-clear-button"></span>
                </div>
              </div>
            </li>
            <li class="item-content item-input">
              <div class="item-inner">
                <div class="item-title item-label input-title">
                  <span>Pricing:</span>
                </div>
                <div class="item-input-wrap">
                  <textarea></textarea>
                  <span class="input-clear-button"></span>
                </div>
              </div>
            </li>
            <li class="item-content item-input">
              <div class="item-inner">
                <div class="item-title item-label input-title">
                  <span>General:</span>
                </div>
                <div class="item-input-wrap">
                  <textarea></textarea>
                  <span class="input-clear-button"></span>
                </div>
              </div>
            </li>
            <li></li>
          </ul>
        </div>
      </div>
      <div id="opportunity_detail_NewOppINT" class="InteractDiv" style="display: none">
        <div class="list">
          <ul>
            <li class="item-content item-input">
              <div class="item-inner">
                <div class="item-title item-label input-title">
                  <span class="">Carrier:</span>
                  <span class="asterisk">*</span>
                </div>
                <div class="item-input-wrap">
                  <select>
                    <option :value="carrierInfo.code" v-for="(carrierInfo, index) in carrierList" :key="carrierInfo.code">{{ carrierInfo.value }}</option>
                  </select>
                </div>
              </div>
            </li>
          </ul>
        </div>
        <div id="chartmain" style="width:40rem; height: 25rem;"></div>
      </div>

    </div>
    <div class="system-status-div">
    <div class="foot-note">
      Last Modified 14/2/19 10:54 (UTC+8) by wongck | Created On 14/2/19 10:54 (UTC+8) by wongck
    </div>
  </div>
    <!--<div class="block block-strong no-padding no-margin margin-bottom">-->
    <!--<div id="demo-picker-date-container"></div>-->
    <!--<div id="opportunity_detail_NewOppGen" class="generalDiv" style="display: none">
      <div class="list"]>
        <ul>
          <li class="item-content item-input">
            <div class="item-inner">
              <div class="item-title item-label input-title">
                <span class="">Carrier:</span>
                <span class="asterisk">*</span>
              </div>
              <div class="item-input-wrap">
                <select>
                  <option :value="carrierInfo.code" v-for="(carrierInfo, index) in carrierList" :key="carrierInfo.code">{{ carrierInfo.value }}</option>
                </select>
              </div>
            </div>
          </li>
          <li class="item-content item-input">
            <div class="item-inner">
              <div class="item-title item-label input-title">
                <span>Sales:</span>
                <span class="asterisk">*</span>
              </div>
              <div class="item-input-wrap">
                <input type="text"  v-model="sail"  @click="popupOpened = true">
                <span class="input-clear-button"></span>
              </div>
            </div>
          </li>
          <li class="item-content item-input">
            <div class="row" style="width: 100%;">
              <div class="col-65">
                <div class="item-inner">
                  <div class="item-title item-label input-title">
                    <span>Customer:</span>
                    <span class="asterisk">*</span>
                  </div>
                  <div class="item-input-wrap">
                    <input type="text"  v-model="customer">
                    <span class="input-clear-button"></span>
                  </div>
                </div>
              </div>
              <div class="col-35">
                <div class="item-inner">
                  <div class="item-title item-label input-title">
                    <span>&nbsp;</span>
                  </div>
                  <div class="item-input-wrap">
                    <input type="text"  v-model="leadTrade">
                    <span class="input-clear-button"></span>
                  </div>
                </div>
              </div>
            </div>
          </li>
          <li class="item-content item-input">
            <div class="row" style="width: 100%;">
              <div class="col-45">
                <div class="item-inner">
                  <div class="item-title item-label input-title">
                    <span>Lead Trade:</span>
                  </div>
                  <div class="item-input-wrap">
                    <input type="text"  v-model="leadTrade">
                    <span class="input-clear-button"></span>
                  </div>
                </div>
              </div>
              <div class="col-45">
                <div class="item-inner">
                  <div class="item-title item-label input-title">
                    <span>Lead Bound:</span>
                  </div>
                  <div class="item-input-wrap">
                    <input type="text"  v-model="leadBouond">
                    <span class="input-clear-button"></span>
                  </div>
                </div>
              </div>
            </div>
          </li>
          <li class="item-content item-input">
            <div class="item-inner">
              <div class="item-title item-label input-title">
                <span>Customer Area:</span>
              </div>
              <div class="item-input-wrap">
                <input type="text"  v-model="customerArea">
                <span class="input-clear-button"></span>
              </div>
            </div>
          </li>
          <li class="item-content item-input">
            <div class="item-inner">
              <div class="item-title item-label input-title">
                <span>Contact Person:</span>
              </div>
              <div class="item-input-wrap">
                <input type="text"  v-model="contactPerson">
                <span class="input-clear-button"></span>
              </div>
            </div>
          </li>
          <li id="tpt">

            <label class="item-checkbox item-content">
              <input type="checkbox" name="demo-checkbox" value="Books" v-model="isTPTUser"/>
              <i class="icon icon-checkbox"></i>
              <div class="item-inner">
                <div class="item-title">TPT EB ISC</div>
              </div>
            </label>
          </li>
          <li class="item-content item-input" style="margin-top: 10px;" v-show="isTPTUser">
            <div class="item-inner">
              <div class="item-title item-label input-title">
                <span>Year:</span>
                <span class="asterisk">*</span>
              </div>
              <div class="item-input-wrap">
                <input type="text"  v-model="customer">
                <span class="input-clear-button"></span>
              </div>
            </div>
          </li>
          <li class="item-content item-input">
            <div class="item-inner">
              <div class="item-title item-label">URL</div>
              <div class="item-input-wrap">
                <input type="url" placeholder="URL">
                <span class="input-clear-button"></span>
              </div>
            </div>
          </li>
          <li></li>
        </ul>
        <button class="button send-email">Send Email</button>
      </div>
    </div>
    <div id="opportunity_detail_NewOppCus" class="ScopeDiv">
      <div class="list">
        <ul>
          <li class="item-content item-input">
            <div class="item-inner">
              <div class="item-title item-label input-title">
                <span class="">Carrier:</span>
                <span class="asterisk">*</span>
              </div>
              <div class="item-input-wrap">
                <select>
                  <option :value="carrierInfo.code" v-for="(carrierInfo, index) in carrierList" :key="carrierInfo.code">{{ carrierInfo.value }}</option>
                </select>
              </div>
            </div>
          </li>
        </ul>
        <div class="scope-block">
          <ul>
            <li class="item-content item-input">
              <div class="item-inner gridHeader">
                <div class="item-title item-label">
                  <span class="" style="float: left; margin-right: 5px;">Opportunity Scope</span>
                  <hr>
                </div>
              </div>
            </li>
            <li class="item-content item-input">
              <div class="item-inner">
                <div class="row">
                  <div class="col scope-field">

                    <div class="row" style="width: 100%;">
                      <div class="item-inner">
                        <div class="row">
                          <div class="item-title item-label input-title">
                            <span>Target Period:</span>
                            <span class="asterisk">*</span>
                          </div>
                        </div>

                        <div class="row">
                          <div class="col-40">
                            <div class="item-input-wrap">
                              <input type="text"  @click="openPicker3"  id="period-from-date">
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                          <div class="col-15">to</div>
                          <div class="col-40">
                            <div class="item-input-wrap">
                              <input type="text"  @click="openPicker2"  id="demo-picker-device">
                              <span class="input-clear-button"></span>
                            </div>
                          </div>

                        </div>

                      </div>


                    </div>
                    <div class="row" style="width: 100%;">
                      <div class="item-inner">
                        <div class="row">
                          <div class="item-title item-label input-title">
                            <span>Cargo Group</span>
                            <span class="asterisk">*</span>
                            <span>/Nature:</span>
                          </div>
                        </div>

                        <div class="row">
                          <div class="col-40">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                          <div class="col-40">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                        </div>

                      </div>

                    </div>
                    <div class="row" style="width: 100%;">
                      <div class="item-inner">
                        <div class="row">
                          <div class="item-title item-label input-title">
                            <span>Biz Nature</span>
                            <span class="asterisk">*</span>
                          </div>
                        </div>

                        <div class="row">
                          <div class="col">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                        </div>

                      </div>

                    </div>


                  </div>
                  <div class="col scope-field">

                    <div class="row" style="width: 100%;">
                      <div class="item-inner">
                        <div class="row">
                          <div class="item-title item-label input-title">
                            <span>Trade</span>
                            <span class="asterisk">*</span>
                            <span>/Lane/Bound:</span>
                          </div>
                        </div>

                        <div class="row">
                          <div class="col-30">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                          <div class="col-30">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                          <div class="col-30">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>

                        </div>

                      </div>


                    </div>
                    <div class="row" style="width: 100%;">
                      <div class="item-inner">

                        <div class="row">
                          <div class="col-30">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                          <div class="col-30">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                          <div class="col-30">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>

                        </div>

                      </div>


                    </div>
                  </div>
                </div>
              </div>
            </li>
          </ul>
        </div>
        <div class="scope-block">
          <ul>
            <li class="item-content item-input">
              <div class="item-inner gridHeader">
                <div class="item-title item-label">
                  <span class="" style="float: left; margin-right: 5px;">Details</span>
                  <hr>
                </div>
              </div>
            </li>
            <li class="item-content item-input">
              <div class="item-inner">
                <div class="row">
                  <div class="col scope-field">
                    <div class="row" style="width: 100%;">
                      <div class="item-inner">
                        <div class="row">
                          <div class="item-title item-label input-title">
                            <span>Status</span>
                            <span class="asterisk">*</span>
                          </div>
                        </div>

                        <div class="row">
                          <div class="col">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                        </div>

                      </div>

                    </div>

                  </div>
                  <div class="col scope-field">
                    <div class="row" style="width: 100%;">
                      <div class="item-inner">
                        <div class="row">
                          <div class="item-title item-label input-title">
                            <span>Likelihood of Success:</span>
                            <span class="asterisk">*</span>
                          </div>
                        </div>

                        <div class="row">
                          <div class="col">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                        </div>

                      </div>

                    </div>

                  </div>
                  <div class="col scope-field">
                    <div class="row" style="width: 100%;">
                      <div class="item-inner">
                        <div class="row">
                          <div class="item-title item-label input-title">
                            <span>Critial Success Factor:</span>
                          </div>
                        </div>

                        <div class="row">
                          <div class="col">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                        </div>

                      </div>

                    </div>

                  </div>
                </div>
              </div>
            </li>
            <li class="item-content item-input">
              <div class="item-inner">
                <div class="row">
                  <div class="col scope-field">
                    <div class="row" style="width: 100%;">
                      <div class="item-inner">
                        <div class="row">
                          <div class="item-title item-label input-title">
                            <span>Expected Vol:</span>
                          </div>
                        </div>

                        <div class="row">
                          <div class="col">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                        </div>

                      </div>

                    </div>

                  </div>
                  <div class="col scope-field">
                    <div class="row" style="width: 100%;">
                      <div class="item-inner">
                        <div class="row">
                          <div class="item-title item-label input-title">
                            <span>Target MQC:</span>
                          </div>
                        </div>

                        <div class="row">
                          <div class="col">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                        </div>

                      </div>

                    </div>

                  </div>
                  <div class="col scope-field">
                    <div class="row" style="width: 100%;">
                      <div class="item-inner">
                        <div class="row">
                          <div class="item-title item-label input-title">
                            <span>Customer Total Annual Vol.(All carriers):</span>
                          </div>
                        </div>

                        <div class="row">
                          <div class="col">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                        </div>

                      </div>

                    </div>

                  </div>
                </div>
              </div>
            </li>
          </ul>
        </div>
        <div class="scope-block">
          <ul>
            <li class="item-content item-input">
              <div class="item-inner gridHeader">
                <div class="item-title item-label">
                  <span class="" style="float: left; margin-right: 5px;">Agreement/Contract</span>
                  <hr>
                </div>
              </div>
            </li>
            <li class="item-content item-input">
              <div class="item-inner">
                <div class="row">
                  <div class="col scope-field">
                    <div class="row" style="width: 100%;">
                      <div class="item-inner">
                        <div class="row">
                          <div class="item-title item-label input-title">
                            <span>Bid Required:</span>
                          </div>
                        </div>

                        <div class="row">
                          <div class="col">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                        </div>

                      </div>

                    </div>

                  </div>
                  <div class="col scope-field">
                    <div class="row" style="width: 100%;">
                      <div class="item-inner">
                        <div class="row">
                          <div class="item-title item-label input-title">
                            <span>Competitors:</span>
                          </div>
                        </div>

                        <div class="row">
                          <div class="col">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                        </div>

                      </div>

                    </div>

                  </div>
                  <div class="col scope-field">
                    <div class="row" style="width: 100%;">
                      <div class="item-inner">
                        <div class="row">
                          <div class="item-title item-label input-title">
                            <span>New Signed Contract/Agreement#:</span>
                          </div>
                        </div>

                        <div class="row">
                          <div class="col">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                        </div>

                      </div>

                    </div>

                  </div>
                  <div class="col scope-field">
                    <div class="row" style="width: 100%;">
                      <div class="item-inner">
                        <div class="row">
                          <div class="item-title item-label input-title">
                            <span>New Signed Contact/Agreement's Effective Period:</span>
                          </div>
                        </div>

                        <div class="row">
                          <div class="col">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                        </div>

                      </div>

                    </div>

                  </div>
                  <div class="col scope-field">
                    <div class="row" style="width: 100%;">
                      <div class="item-inner">
                        <div class="row">
                          <div class="item-title item-label input-title">
                            <span>New Signed Contract/Agreement's MQC:</span>
                          </div>
                        </div>

                        <div class="row">
                          <div class="col">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                        </div>

                      </div>

                    </div>

                  </div>
                </div>
              </div>
            </li>
          </ul>
        </div>
        <div class="scope-block">
          <ul>
            <li class="item-content item-input">
              <div class="item-inner gridHeader">
                <div class="item-title item-label">
                  <span class="" style="float: left; margin-right: 5px;">References</span>
                  <hr>
                </div>
              </div>
            </li>
            <li class="item-content item-input">
              <div class="item-inner">
                <div class="row">
                  <div class="col scope-field">

                    <div class="row" style="width: 100%;">
                      <div class="item-inner">

                        <ul style="padding: 0;">
                          <li style="padding: 0;" class="item-content item-input">
                            <div class="item-inner">
                              <div class="item-title item-label input-title">
                                <span>Services:</span>
                              </div>
                              <div class="item-input-wrap">
                                <input id="autocomplete-dropdown" type="text" placeholder="Fruit">
                              </div>
                            </div>
                          </li>
                        </ul>

                        <div class="row">
                          <div class="col-30">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                          <div class="col-30">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                          <div class="col-30">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>

                        </div>

                      </div>


                    </div>
                    <div class="row" style="width: 100%;">
                      <div class="item-inner">

                        <div class="row">
                          <div class="col-30">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                          <div class="col-30">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                          <div class="col-30">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>

                        </div>

                      </div>


                    </div>
                  </div>
                  <div class="col scope-field">

                    <div class="row" style="width: 100%;">
                      <div class="item-inner">
                        <div class="row">
                          <div class="item-title item-label input-title">
                            <span>Total TPP Volume:</span>
                          </div>
                        </div>

                        <div class="row">
                          <div class="col-75">
                            <div class="item-input-wrap">
                              <input type="text">
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                          <div class="col-20">
                            <div class="item-input-wrap">
                              <input type="text">
                              <span class="input-clear-button"></span>
                            </div>
                          </div>

                        </div>

                      </div>


                    </div>
                    <div class="row" style="width: 100%;">
                      <div class="item-inner">
                        <div class="row">
                          <div class="item-title item-label input-title">
                            <span>Total TPP Volume:</span>
                          </div>
                        </div>

                        <div class="row">
                          <div class="col-75">
                            <div class="item-input-wrap">
                              <input type="text"  @click="openPicker3"  id="period-from-date">
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                          <div class="col-20">
                            <div class="item-input-wrap">
                              <input type="text"  @click="openPicker2"  id="demo-picker-device">
                              <span class="input-clear-button"></span>
                            </div>
                          </div>

                        </div>

                      </div>


                    </div>
                    <div class="row" style="width: 100%;">
                      <div class="item-inner">
                        <div class="row">
                          <div class="item-title item-label input-title">
                            <span>Commodity</span>
                          </div>
                        </div>

                        <div class="row">
                          <div class="col">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                        </div>

                      </div>

                    </div>
                    <div class="row" style="width: 100%;">
                      <div class="item-inner">
                        <div class="row">
                          <div class="item-title item-label input-title">
                            <span>Size/Type:</span>
                          </div>
                        </div>

                        <div class="row">
                          <div class="col">
                            <div class="item-input-wrap">
                              <input type="text"  >
                              <span class="input-clear-button"></span>
                            </div>
                          </div>
                        </div>

                      </div>

                    </div>


                  </div>
                </div>
              </div>
            </li>
          </ul>
        </div>
        &lt;!&ndash;<div class="block block-strong no-padding no-margin margin-bottom">&ndash;&gt;
          &lt;!&ndash;<div id="demo-picker-date-container"></div>&ndash;&gt;
        &lt;!&ndash;</div>&ndash;&gt;

      </div>
    </div>-->



    <div class="customer-picker"
         style="display: none; border:solid 1px #000000; background: #e1e11e;z-index: 500; position: absolute; width: 280px; height: 190px;">
      <div class="head"><span>head</span></div>
      <div class="date-content">
        <div class="add-div" style="display: flex;">
          <div class="add-month" style="width: 50%">+</div>
          <div class="add-year" style="width: 50%">+</div>
        </div>
        <div class="date-div " style="display: flex;">
          <div class="month" style="width: 50%">1</div>
          <div class="year" style="width: 50%">2</div>
        </div>
        <div class="sub-div" style="display: flex;">
          <div class="sub-month" style="width: 50%">-</div>
          <div class="sub-month" style="width: 50%">-</div>
        </div>

      </div>
    </div>
    <f7-popup class="demo-popup" :tablet-fullscreen="true" :opened="popupOpened" @popup:closed="popupOpened = false">
      <f7-page theme-dark style="background: #1c1c1d;">
        <f7-navbar>
          <f7-nav-left>
            <f7-link popup-close>Close</f7-link>
          </f7-nav-left>
          <f7-nav-title>Popup Title</f7-nav-title>
          <f7-nav-right>
            <f7-link popup-close></f7-link>
          </f7-nav-right>
        </f7-navbar>
        <div class="list popup-page">
          <ul style="margin-top: 35px; padding: 0;">
            <li class="item-content item-input popup-input-item">
              <div class="item-inner">

                <div class="item-input-wrap">
                  <input class="popup-input" type="text" style="height: 25px; line-height: 24px; color: black;" placeholder="Search Sales">
                  <span class="input-clear-button"></span>
                </div>
              </div>
            </li>

          </ul>
        </div>
      </f7-page>
    </f7-popup>
  </f7-page>

</template>
<script>
  // import popup from './popup.vue'

  export default {
    data: function () {
      return {
        popupOpened: false,
        carrier: "COSCO",
        carrierList: [
          {code: "1", value: "COSCO"},
          {code: "2", value: "COSCOSEA"},
          {code: "3", value: "PANASIA"},
        ],
        tradeList: [
          {code: 'Any', value: 'Any'},
          {code: 'AET', value: 'AET'},
          {code: 'AAT', value: 'AAT'},
          {code: 'CCT', value: 'CCT'},
          {code: 'JKT', value: 'JKT'},
          {code: 'IAT', value: 'IAT'},
          {code: 'ICT', value: 'ICT'},
          {code: 'IET', value: 'IET'},
          {code: 'AUT', value: 'AUT'},
        ],
        sizeTypeArray: [],
        tradeArray: [],
        sizeTypeList: [
          "20GP",
          "20FL",
          "20RQ"
        ],
        sail: "C K Wong",
        customer: "Test111",
        leadTrade: "Any",
        leadBouond: "Any",
        customerArea: "ZhuHai",
        contactPerson: "Test Person",
        isTPTUser: false,
        currentDiv: "general",
        option: {
          title: {
            text: 'ECharts 数据统计'
          },
          tooltip: {},
          legend: {
            data: ['用户来源']
          },
          xAxis: {
            data: ["Android", "IOS", "PC", "Ohter"]
          },
          yAxis: {},
          series: [{
            name: '访问量',
            type: 'line',
            data: [500, 200, 360, 100]
          }]
        },
      }
    },
    mounted: function () {
      var fruits = ('Apple Apricot Avocado Banana Melon Orange Peach Pear Pineapple').split(' ');
      var autocompleteDropdownSimple = this.$f7.autocomplete.create({
        inputEl: '#autocomplete-dropdown',
        openIn: 'dropdown',
        source: function (query, render) {
          var results = [];
          if (query.length === 0) {
            render(results);
            return;
          }
          // Find matched items
          for (var i = 0; i < fruits.length; i++) {
            if (fruits[i].toLowerCase().indexOf(query.toLowerCase()) >= 0) {
              results.push(fruits[i]);
            }
          }
          // Render items by passing array with result items
          render(results);
        }
      });
    },
    methods: {
      itemClick: function (value) {
        let currentClass = '.' + value
        this.$$('.button-active').removeClass('button-active')
        this.$$(currentClass).addClass('button-active')
        let selectedDiv = this.$$(currentClass).attr("href")
        this.$$(selectedDiv).siblings().hide()
        // this.showLoading()
        // this.hideLoading()
        this.$$(selectedDiv).show()
        if (value === 'int') {
          var echarts = require('../echarts.js')
          let chartmain = document.getElementById('chartmain')
          let myChart = echarts.init(document.getElementById('chartmain'));
          console.log(myChart)

          //使用制定的配置项和数据显示图表
          myChart.setOption(this.option);
        }
      },
      popupClick: function () {
        /*var popup = this.$f7.popup.create({
          content: '<div class="popup">...</div>',
          on: {
            opened: function () {
              console.log('Popup opened')
            }
          }
        })*/
        // var popup = this.$f7.get(".popup-about")
        // popup.open()
      },
      openPicker3: function (e) {
        console.log(e)
        let picker = this.$$('.customer-picker')
        picker.css('top', e.clientY + 'px')
        picker.css('left', e.clientX + 'px')

      },
      openPicker2: function () {
        let pickerDevice = this.$f7.picker.create({
          inputEl: '#demo-picker-device',
          openIn: 'popover',
          cols: [
            {
              textAlign: 'center',
              values: ['iPhone 4', 'iPhone 4S', 'iPhone 5', 'iPhone 5S', 'iPhone 6', 'iPhone 6 Plus', 'iPad 2', 'iPad Retina', 'iPad Air', 'iPad mini',
                'iPad mini 2', 'iPad mini 3']
            }
          ]
        });
      },
      openPicker: function () {
        let today = new Date();
        let pickerCustomToolbar = this.$f7.picker.create({
          inputEl: '#period-from-date',
          // openIn: 'popover',
          rotateEffect: false,
          render: function () {
            let valueString = '<div class="picker-items>"'
            for (let i = 0; i < this.cols[0].values.length; i++) {
              console.log(this.cols[0].values[i])
              valueString += '<div class="picker-item" data-picker-value="' + this.cols[0].values[i]
                + '"><span>' + this.cols[0].values[i] + '</span></div>'
            }
            valueString += '</div>'
            // return "<div class='popover picker-popover'><div class='picker'><div class='picker-columns'><div class='picker-column'>"
            //   + valueString
            //   + "</div></div></div>"
            return '<div class="popover picker-popover" style="display: block; top: 43px; left: 232.125px;"><div class="popover-angle on-bottom" style="left: 127px;"></div>\n'
              + '        <div class="popover-inner">\n'
              + '          <div class="picker  ">\n'
              + '            <div class="toolbar no-shadow">\n'
              + '        <div class="toolbar-inner">\n'
              + '          <div class="left"></div>\n'
              + '          <div class="right">\n'
              + '            <a href="#" class="link sheet-close popover-close">Done</a>\n'
              + '          </div>\n'
              + '        </div>\n'
              + '      </div>\n'
              + '            <div class="picker-columns">\n'
              + '              <div class="picker-column picker-column-center picker-column-first picker-column-last">\n'
              + '          <div class="picker-items" style="transform: translate3d(0px, 60px, 0px); transition-duration: 0ms;">\n'
              + '        <div class="picker-item picker-item-selected" data-picker-value="iPhone 4" style="transition-duration: 0ms;">\n'
              + '          <span>iPhone 4</span>\n'
              + '        </div>\n'
              + '      \n'
              + '        <div class="picker-item" data-picker-value="iPhone 4S" style="transition-duration: 0ms;">\n'
              + '          <span>iPhone 4S</span>\n'
              + '        </div>\n'
              + '      \n'
              + '        <div class="picker-item" data-picker-value="iPhone 5" style="transition-duration: 0ms;">\n'
              + '          <span>iPhone 5</span>\n'
              + '        </div>\n'
              + '      \n'
              + '        <div class="picker-item" data-picker-value="iPhone 5S" style="transition-duration: 0ms;">\n'
              + '          <span>iPhone 5S</span>\n'
              + '        </div>\n'
              + '      \n'
              + '        <div class="picker-item" data-picker-value="iPhone 6" style="transition-duration: 0ms;">\n'
              + '          <span>iPhone 6</span>\n'
              + '        </div>\n'
              + '      \n'
              + '        <div class="picker-item" data-picker-value="iPhone 6 Plus" style="transition-duration: 0ms;">\n'
              + '          <span>iPhone 6 Plus</span>\n'
              + '        </div>\n'
              + '      \n'
              + '        <div class="picker-item" data-picker-value="iPad 2" style="transition-duration: 0ms;">\n'
              + '          <span>iPad 2</span>\n'
              + '        </div>\n'
              + '      \n'
              + '        <div class="picker-item" data-picker-value="iPad Retina" style="transition-duration: 0ms;">\n'
              + '          <span>iPad Retina</span>\n'
              + '        </div>\n'
              + '      \n'
              + '        <div class="picker-item" data-picker-value="iPad Air" style="transition-duration: 0ms;">\n'
              + '          <span>iPad Air</span>\n'
              + '        </div>\n'
              + '      \n'
              + '        <div class="picker-item" data-picker-value="iPad mini" style="transition-duration: 0ms;">\n'
              + '          <span>iPad mini</span>\n'
              + '        </div>\n'
              + '      \n'
              + '        <div class="picker-item" data-picker-value="iPad mini 2" style="transition-duration: 0ms;">\n'
              + '          <span>iPad mini 2</span>\n'
              + '        </div>\n'
              + '      \n'
              + '        <div class="picker-item" data-picker-value="iPad mini 3" style="transition-duration: 0ms;">\n'
              + '          <span>iPad mini 3</span>\n'
              + '        </div>\n'
              + '      </div>\n'
              + '        </div>\n'
              + '              <div class="picker-center-highlight"></div>\n'
              + '            </div>\n'
              + '          </div>\n'
              + '        </div>\n'
              + '      </div>'
          },
          cols: [
            {
              values: ['Mr', 'Ms'],
            },
            // {
            //   textAlign: 'left',
            //   values: ('Super Amazing Bat Iron Rocket Lex Beautiful Wonderful Raining Happy Funny Cool Hot').split(' ')
            // },
            // {
            //   values: ('Man Luthor Woman Boy Girl Person Cutie Babe Raccoon').split(' ')
            // },
          ],
        });
        // pickerCustomToolbar.open()
      },
      autocompleteService: function () {

      },
      addTradeArray: function () {
        this.tradeArray.push(
          {trade: "Any", Bound: "Any", Lane: "Any"}
        )
      },
      addSizeArray: function () {
        this.sizeTypeArray.push(
          "20GP"
        )
      },
      delTradeInfo: function (index) {
        this.tradeArray.splice(index, 1)
      },
      delSizeType: function(index) {
        this.sizeTypeArray.splice(index, 1)
      },

      showLoading: function () {
        this.$f7.preloader.show();
      },
      hideLoading: function () {
        setTimeout(() => {
          this.$f7.preloader.hide();
        }, 1000);
      },

    },
    components: {
      // popup
    }
  }
</script>
<style scoped type="scss">

  @media screen and (min-width: 678px) {
    .navbar-theme {
      float: none;
      clear: both;
      padding: 0;
      max-width: 66%;
      margin-left: auto;
      margin-right: auto;
    }

    .send-email {
      border: solid 1px;
      margin-top: 1.3em !important;
      border-radius: .4em !important;
      width: 40%;
      left: 30%;
      height: 50px;
      font-size: 20px;
      border-right-width: 1px !important;
      border-left-width: 1px !important;
    }

    .popup-page {
      float: none;
      clear: both;
      padding: 0;
      max-width: 66%;
      margin-left: auto;
      margin-right: auto;
    }

    #sail .scope-field {
      width: 49%;
    }
  }

  @media screen and (max-width: 678px) {
    #sail .scope-field {
      width: 98%;
    }
    .send-email {
      border: solid 1px;
      margin-top: 1.3em !important;
      font-size: 20px;
      height: 30px;
      border-radius: 0px;
    }

    .popup-page {
      width: 100%;
    }
  }

  .navbar-theme {
    background: white;
  }

  #main-view .navbar {
    background: white;
  }

  #tpt .item-inner:after {
    height: 0;
  }

  .list .item-inner {
    padding-right: 0;
  }

  .list .item-inner:after {
    height: 0;
  }

  .row {
    width: 100%;
  }

  .item-input-wrap {
    width: 100%;
    border-bottom: solid 1px #e1e1e1;
  }

  .input-title {
    color: gray;
    font-size: .85rem;
  }

  .asterisk {
    color: red;
  }

  .subnavbar-inner {
    padding: 0 15px;
  }

  .subnavbar:after {
    height: 0;
  }

  .subnavbar-border button {
    border-right: solid 1px purple;
  }

  .subnavbar-border button:last-child {
    border-right: 0;
  }

  .list ul:before {
    height: 0;
  }

  .list ul:after {
    height: 0;
  }

  .list .item-content {
    padding: 0 30px;
  }

  .popup-input-item {
    padding: 0;
  }

  .popup-input {
    background: #ffffff;
    border-radius: 5px;
    /*height: 1.5rem;*/
  }

  textarea {
    margin-top: 10px;
    height: 50px;
  }

  .system-status-div {
    /*position: absolute;*/
    /*bottom: 10px;*/
  }

  .foot-note {
    margin-left: 15px !important;
    margin-right: 15px !important;
    position: absolute;
    bottom: 60px;
    left: inherit;
    width: initial;
    text-align: left;
  }

  .gridHeader {
    margin-top: 15px;
    color: #573590;
  }

  .gridHeader span {
    font-size: 20px;
    font-style: italic;
    display: block;
    float: left;
    font-weight: normal;
    margin-right: 10px;
  }

  .gridHeader hr {
    padding-top: 11px;
    border: 0;
    border-bottom: 1px solid;
  }
</style>
