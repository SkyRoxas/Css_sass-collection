sass-collection
===============
> SASS庫集合及使用方式，喜歡的朋友就Star一下吧^ _ ^
> 也歡迎其他朋友們一起跟我們分享更好的sass mixin跟給我們一些指教唷。感謝～

## 貢獻方式

+ Fork 這個項目
+ 將您個人收藏的sass mixin新增至mixin資料夾中。
+ 並將你新增的 mixin在 _sass-code.scss 引入進去。
+ 分享一下如何使用mixin幫我們寫在README.md中。
+ 保存並提交
+ 新建一個 Pull Request

##使用方式


###引入sass-collection

~~~~
@import "_sass-code.scss";
~~~~

###bootstrap-grid 使用

####html架構

~~~~
<div class="wrap">
	<div class="row">
		<div class="column"></div>
		<div class="column"></div>
	</div>
</div>

~~~~
####include方式

*gutter_custom可自行定義*

+ exp:@include container-fixed(30px);
+ make-xs-column: 480px 以上切多少column
+ make-sm-column: 768px 以上切多少column
+ make-md-column: 992px 以上切多少column
+ make-lg-column:1200px 以上切多少column

~~~~
.wrap{
	@include container-fixed(gutter_custom);
}
~~~~
~~~~
.row{
	@include make-row(15px, 15px);//此範例左右margin:-15px
}
~~~~
~~~~
.column{
	@include make-xs-column(6);//此範例視窗寬度大於480以上的時候變width:50%
	@include gutter(30px,30px);//此範例左右padding:15px
}
~~~~

以下範例針對四種視窗做設定

~~~~
.column{
	@include make-xs-column(2);//此範例視窗寬度大於480以上的時候切6塊
	@include make-sm-column(3);//此範例視窗寬度大於768以上的時候切4塊
	@include make-md-column(4);//此範例視窗寬度大於992以上的時候切3塊
	@include make-lg-column(6);//此範例視窗寬度大於1200以上的時候切2塊
}
~~~~

進階用法 

可定義div要向左向右推多少column

~~~~
.column{
	@include make-sm-column-offset(2);
}

.column{
	@include make-sm-column-push(2);
}

.column{
	@include  make-sm-column-pull(2);
}
~~~~










