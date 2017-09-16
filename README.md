# -RWD-Sassw/0mediaquery
breakpoint with calc/width/max-width/min-width

    @mixin break($bp: 400px, $ltbp: 100%, $gtbp: 50%)
      max-width: $ltbp
      width: calc((#{$bp} - 100%) * 1000)
      min-width: $gtbp
  
第一個參數為要設定的斷點(螢幕大小)

第二個為小於那個斷點時所見的寬度

第三個為大於那個斷點時的寬度

預設斷點設定為400px

容器寬度 100% 如果大於400, 例如 450

(400px -450 = -50px) * 1000 = -50000px (< 0) , min-width生效 寬度即為 500%



容器寬度 100% 如果小於400, 例如350

(400px -350 = 50px) * 1000 = 50000px (> 0) , max-width生效 寬度即為100%



=> 簡而言之, 將容器(視窗)慢慢縮小, 小於400px之後寬度就變成滿版(100%). 
