<!-- HTML 시작 !-->
<div id="app">
  <v-app id="inspire">
      <div>
      <v-row no-gutters>
      <v-card color="black" width="100%">
        <div style='text-align:center'>
          <span class="time">2020-03-14 12:00:00</span>
        </div>
      </v-card>
      <v-responsive width="100%"></v-responsive>
        <template v-for="item in machine">
          <v-col :key="item.idx">
            <v-card class="item-container">
              <v-row>
                <v-toolbar dense flat color="#b5b5b5" class="height-30">
                  <span class="f_mname">{{item.mid}}</span>
                    <v-spacer></v-spacer>
                  <span class="f_p">{{item.process}}</span>
                </v-toolbar>
	            </v-row>
	            <div class="text-center height-40">
	              <span class="f_end" style="align:center">{{item.timer}}</span>
	            </div>
	      	    <v-footer :fixed="true"  absolute class="white height-30">
	              <v-row>
	                <v-progress-linear value="15"
                    color="#357d21" background-color="#828282" rounded>
                    <v-flex style="maxWidth:20px"></v-flex>
                    <span class="vt">{{ item.count}}</span>
                    <v-spacer></v-spacer>
                    <span class="vt">
                      <div class="text-right">{{ item.fTime }}</div>
                    </span>
                    <v-flex style="maxWidth:20px"></v-flex>
	                </v-progress-linear>
	              </v-row>
	            </v-footer>
            </v-card>
          </v-col>
        </template>
  </v-app>
</div>

<!-- HTML 끝 !-->

<style>
<!-- CSS 시작 !-->
.col {
  min-width:33.3%;
  height:calc(50vh - 6.5vh);
  position:relative;
}
.time{
	font-size: 3vw;
	color: #f4fc03;
	text-align: center;
}
.f_mname{
/* 	margin: 30px; */
	font-size: 5vh;
}
.f_p {
	font-size: 2vh;
  white-space : nowrap;
/* 	margin: 20px; */
}
.vt {
	font-size: 2vw;
	color: #ffffff;
}
.f_end {
	font-size: 15vh;
}
.item-container {
  height:100% !important;
  position:relative;
}
.v-toolbar__content {
  /*height:100% !important;*/
/*   align-items: baseline !important; */
}
.row > header {
  height:auto !important;
}
.v-progress-linear__content {
  height:100%;
}
.v-progress-linear {
  height:10vh !important;
}
.v-footer {
  padding:0 16px;
}

.height-30 {
  height: 30% !important;
}

.height-40 {
  height: 40% !important;
}
.v-toolbar__content {flex-wrap:wrap;}
.v-toolbar__content .f_mname {line-height:3.5rem;}
.v-toolbar__content span {display:inline-block;height:100%;line-height:4.5rem;}
.item-container > .row {padding: 0 12px;}
@media screen and (max-width: 416px) and (min-width: 10px) {
  .col {height:calc(50vh - 3.2vh);}
  .v-toolbar__content span {height:auto !important;}
  .v-toolbar__content .f_mname {
    font-size:4vw !important;
    line-height:initial !important;
  }
  .f_p {
    font-size : 2vw !important;
    line-height:initial!important;
    width:100%;
  }
  .f_end {font-size:10vh;}
  .v-toolbar__content, .v-toolbar__extension {
    padding: 0 0 0 6px;

  }
}
@media screen and (max-width: 360px) and (min-width: 10px) {
  .col {height:calc(50vh - 4vh);}
}

<!-- CSS 끝 !-->
</style>
<script>
<!-- JS 시작 !-->
new Vue({
	  el: '#app',
	  vuetify: new Vuetify(),
	  data () {
	    return {
	      tab: null,
	      machine: [
	        {
	          mid : 'Puma280',
	          idx : 1,
	          process : 'CS98D25H49-01-2',
	          timer : '가공완료',
	          count : '100/100',
	          fTime : '0 시간 6 분',

	        },
	        {
	          mid : 'PumaV400',
	          idx : 2,
	          process : 'O0229',
	          timer : '04:34',
	          count : '4/100',
	          fTime : '84 시간 40 분',

	        },
	        {
	          mid : 'Lynx220C',
	          idx : 3,
	          process : 'D580007-02-F',
	          timer : '01:33',
	          count : '459/500',
	          fTime : '2 시간 36 분',

	        },
	        {
	          mid : 'Puma240',
	          idx : 4,
	          process : 'WGR150D35H24-02-1',
	          timer : '00:10',
	          count : '70/100',
	          fTime : '1 시간 31 분',

	        },
	        {
	          mid : 'Lynx220CL',
	          idx : 5,
	          process : 'CS98D25H49-02-02',
	          timer : '02:34',
	          count : '12/100',
	          fTime : '5 시간 0 분',

	        },
	        {
	          mid : 'Lynx220SY',
	          idx : 6,
	          process : 'JIG-CD',
	          timer : 'READY',
	          count : '110/200',
	          fTime : '23 시간 48 분',

	        },
	      ],
	    }
	  },
	})
<!-- JS 끝 !-->
</script>
