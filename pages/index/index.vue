<template>
	<view class="content">
	 
		<view class="header_box">
			
			<view class="tite_box"> 商城 </view>
			
			<view class="search_box">
				<view class="input_box">
					<image class="search_icon" src="/static/images/search_icon.png"></image>
					<input disabled  placeholder="点击搜索更多" class="input" type="text">
				</view> 
				<view class="coupon_box">
					<image class="coupon_icon" src="/static/images/coupon_icon.png"></image>
					<view class="coupon_text">领券</view>
					<image class="coupon_right_icon" src="/static/images/right_icon.png"></image>
				</view>  
			</view>	
			
			<view class="ad_box">
				 <image class="ad_img" src="/static/images/ad_img.png"></image>
				 <view class="ad_text">正品保真</view>	
			</view>	
			
		</view>	
		<view class="main_box">
			
			<view class="main_inner_box">
				
				<view class="main_left_box">
					<!-- 一级菜单区域 -->
					<scroll-view   :scroll-into-view="scrollInex"   scroll-with-animation='true'  scroll-y="true" class="menu_list"   >
						 <view @click="change_one_index(index)" :id="'scrollInex' + index "  v-for="(item,index) in cate_list" :key="item.id" :class="['menu_item', index == cate_one_index ? 'active' : ''] " >{{item.name}}</view> 
						 <view class="menu_bottom"></view>
					</scroll-view>
					
				</view>   
				
				
				<view class="main_right_box">
					 
					 <view class="main_right_top_box">
						  
							<!-- 轮播图 -->
							<swiper class="swiper"  indicator-active-color="#FFFFFF" indicator-color="#D4D4D4" :duration="500" circular :indicator-dots="true" :autoplay="true" :interval="3000"
								 >
								<swiper-item>
									<view class="swiper-item">
										<image class="swiper_item_img" mode="aspectFill" src="https://zjzdd.oss-cn-beijing.aliyuncs.com/public/uploads/goods/1690452261_60148.jpg"></image>
									</view>
								</swiper-item>
								 
								 <swiper-item>
								 	<view class="swiper-item">
								 		<image class="swiper_item_img" mode="aspectFill" src="https://zjzdd.oss-cn-beijing.aliyuncs.com/public/uploads/goods/1690452261_60148.jpg"></image>
								 	</view>
								 </swiper-item>
								 <swiper-item>
								 	<view class="swiper-item">
								 		<image class="swiper_item_img" mode="aspectFill" src="https://zjzdd.oss-cn-beijing.aliyuncs.com/public/uploads/goods/1690452261_60148.jpg"></image>
								 	</view>
								 </swiper-item>
							</swiper>
								 
							<!-- 排序筛选 -->
							<view class="sort_list_box"> 
								<view @click="change_sort_index(index)" v-for="(item,index) in sort_list" :key="item.id" :class="['sort_item', index == sort_index ? 'active' : ''] " >{{item}}</view>
							 </view>
							 
							<!-- 二级分类 --> 
							<view class="sort_row_box"> 
								<scroll-view  :scroll-into-view="scrollId" scroll-x="true"  scroll-with-animation='true' class="sort_row_list">
									 <view @click="change_nav(index)"  v-for="(item,index) in cate_two_list" :id="'scrollId' + index " :class="['cate_two_item', index == cate_two_index ? 'active' : ''] " >{{item.name}} </view>
								</scroll-view>
							</view>  
						 
					 </view>
					 
					 <!-- 商品列表 -->
					 <view class="goods_box">
						 
						 <scroll-view scroll-with-animation='true'  scroll-y="true" class="goods_list"   >
						 	 <!-- <view @click="change_one_index(index)"   v-for="(item,index) in cate_list" :key="item.id" :class="menu_item" >{{item.name}}</view> -->
							 
							<view class="goods_item">
								<view class="goods_img_box">
									<image class="goods_img" src="https://zjzdd.oss-cn-beijing.aliyuncs.com/public/uploads/goods/1690452261_60148.jpg"></image>
								</view>	
								<view class="goods_info_box">
									<view class="goods_title ">珠江原浆啤酒11°P听装980m*1/6[冰镇]</view>	
									<view class="goods_label_box">
										<view class="label_one_text"> 提供冰镇 </view> 
										<view class="label_two_text"> 1.3w酒友常喝 </view>
									</view>	
									
									<view class="discount_box">
										<view class="vip_text"> vip </view>
										<view class="discount_text"> 8.6折</view>
									</view>
									
									
									<view class="new_tag_wapper">
										<view class="new_tag_box">
											<view class="new_text"> 新人 </view>
											<view class="new_tag_text"> 专享价</view>
										</view>
										
										<view class="new_tag_box">
											<view class="new_text"> 新人 </view>
											<view class="new_tag_text"> 买一送一</view>
										</view>
									</view>
									
									
									<view class="buy_info">
										<view class="price_box">
											<text class="price_icon">￥</text>
											<text class="price_text">6.00</text>
											<text class="price_tip_text">起</text>
											<text class="market_price_text">￥28.00</text> 
										</view>
										<button @click="open_buy_dialog" class="buy_btn">购买</button>
									</view>
									  
								</view>	
							</view>
							
							<view class="goods_item">
								<view class="goods_img_box">
									<image class="goods_img" src="https://zjzdd.oss-cn-beijing.aliyuncs.com/public/uploads/goods/1690452261_60148.jpg"></image>
								</view>	
								<view class="goods_info_box">
									<view class="goods_title">珠江原浆啤酒11°P听装980m*1/6[冰镇]</view>	
									<view class="goods_label_box">
										<view class="label_one_text"> 提供冰镇 </view> 
										<view class="label_two_text"> 1.3w酒友常喝 </view>
									</view>	
									
									<view class="discount_box">
										<view class="vip_text"> vip </view>
										<view class="discount_text"> 8.6折</view>
									</view>
									
									
									<view class="new_tag_wapper">
										<view class="new_tag_box">
											<view class="new_text"> 新人 </view>
											<view class="new_tag_text"> 专享价</view>
										</view>
										
										<view class="new_tag_box">
											<view class="new_text"> 新人 </view>
											<view class="new_tag_text"> 买一送一</view>
										</view>
									</view>
									
									
									<view class="buy_info">
										<view class="price_box">
											<text class="price_icon">￥</text>
											<text class="price_text">6.00</text>
											<text class="price_tip_text">起</text>
											<text class="market_price_text">￥28.00</text> 
										</view>
										<button class="buy_btn">购买</button>
									</view>
									  
								</view>	
							</view>
							
							
							<view class="goods_item">
								<view class="goods_img_box">
									<image class="goods_img" src="https://zjzdd.oss-cn-beijing.aliyuncs.com/public/uploads/goods/1690452261_60148.jpg"></image>
								</view>	
								<view class="goods_info_box">
									<view class="goods_title">珠江原浆啤酒11°P听装980m*1/6[冰镇]</view>	
									<view class="goods_label_box">
										<view class="label_one_text"> 提供冰镇 </view> 
										<view class="label_two_text"> 1.3w酒友常喝 </view>
									</view>	
									
									<view class="discount_box">
										<view class="vip_text"> vip </view>
										<view class="discount_text"> 8.6折</view>
									</view>
									
									
									<view class="new_tag_wapper">
										<view class="new_tag_box">
											<view class="new_text"> 新人 </view>
											<view class="new_tag_text"> 专享价</view>
										</view>
										
										<view class="new_tag_box">
											<view class="new_text"> 新人 </view>
											<view class="new_tag_text"> 买一送一</view>
										</view>
									</view>
									 
									<view class="buy_info">
										<view class="price_box">
											<text class="price_icon">￥</text>
											<text class="price_text">6.00</text>
											<text class="price_tip_text">起</text>
											<text class="market_price_text">￥28.00</text> 
										</view>
										<button class="buy_btn">购买</button>
									</view>
									  
								</view>	
							</view>
							  
						 </scroll-view>
						 
					 </view>
					 
				</view> 
				
			</view> 
			
			
			<!-- 筛选的弹窗 -->
			<view class="dialog_fixed" v-if="dialog_screen_box">
				<view class="screen_box">
					<view class="screen_top_box">
						<view class="screen_top_cate_text">全部分类</view>
						<view class="screen_top_up_text" @click="dialog_screen_box = false">
							收起
							<image class="up_icon" src="/static/images/up_icon.png"></image>
						</view>
					</view>	
					<view class="screen_cate_box">
						 
						 <view class="screen_cate_list">
							 
							 <view class="screen_cate_item">
							 	<view class="screen_cate_left">
							 		<image class="goods_img" src="https://zjzdd.oss-cn-beijing.aliyuncs.com/public/uploads/goods/1690452261_60148.jpg"></image>
							 		<view class="screen_cate_left_title">水果鲜花</view>						 
							 	</view>	
								<view class="screen_cate_right">
									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
								</view>	
							 </view>
							 
							 
							 <view class="screen_cate_item">
							 	<view class="screen_cate_left active">
							 		<image class="goods_img" src="https://zjzdd.oss-cn-beijing.aliyuncs.com/public/uploads/goods/1690452261_60148.jpg"></image>
							 		<view class="screen_cate_left_title">水果鲜花</view>						 
							 	</view>	
								<view class="screen_cate_right">
									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
									<view class="screen_cate_right_item active"> 精酿啤酒 </view>							 
									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
								</view>	
							 </view>
							 
							 
							 
							 <view class="screen_cate_item">
							 	<view class="screen_cate_left">
							 		<image class="goods_img" src="https://zjzdd.oss-cn-beijing.aliyuncs.com/public/uploads/goods/1690452261_60148.jpg"></image>
							 		<view class="screen_cate_left_title">水果鲜花</view>						 
							 	</view>	
								<view class="screen_cate_right">
									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
								</view>	
							 </view>
							 
							 
							 
							 <view class="screen_cate_item">
							 	<view class="screen_cate_left">
							 		<image class="goods_img" src="https://zjzdd.oss-cn-beijing.aliyuncs.com/public/uploads/goods/1690452261_60148.jpg"></image>
							 		<view class="screen_cate_left_title">水果鲜花</view>						 
							 	</view>	
							 								<view class="screen_cate_right">
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 								</view>	
							 </view>
							 
							 <view class="screen_cate_item">
							 	<view class="screen_cate_left">
							 		<image class="goods_img" src="https://zjzdd.oss-cn-beijing.aliyuncs.com/public/uploads/goods/1690452261_60148.jpg"></image>
							 		<view class="screen_cate_left_title">水果鲜花</view>						 
							 	</view>	
							 								<view class="screen_cate_right">
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 								</view>	
							 </view>
							 
							 
							 
							 <view class="screen_cate_item">
							 	<view class="screen_cate_left">
							 		<image class="goods_img" src="https://zjzdd.oss-cn-beijing.aliyuncs.com/public/uploads/goods/1690452261_60148.jpg"></image>
							 		<view class="screen_cate_left_title">水果鲜花</view>						 
							 	</view>	
							 								<view class="screen_cate_right">
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 								</view>	
							 </view>
							 
							 
							 <view class="screen_cate_item">
							 	<view class="screen_cate_left">
							 		<image class="goods_img" src="https://zjzdd.oss-cn-beijing.aliyuncs.com/public/uploads/goods/1690452261_60148.jpg"></image>
							 		<view class="screen_cate_left_title">水果鲜花</view>						 
							 	</view>	
							 								<view class="screen_cate_right">
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 									<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
							 								</view>	
							 </view>
							 
							 
							 
							 <view class="screen_cate_item">
							 	<view class="screen_cate_left">
							 		<image class="goods_img" src="https://zjzdd.oss-cn-beijing.aliyuncs.com/public/uploads/goods/1690452261_60148.jpg"></image>
							 		<view class="screen_cate_left_title">水果鲜花</view>						 
							 	</view>	
									<view class="screen_cate_right">
										<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
										<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
										<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
										<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
										<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
										<view class="screen_cate_right_item"> 精酿啤酒 </view>							 
									</view>	
							 </view>
							 
							 
							 
							 
						 </view>
					</view>	
				</view>
			</view>
			 
		</view>	 
	    
	   
	   <view class="dialog_fixed_box" v-if="is_show_dialog"></view>
	   
	   <!-- 购买的弹窗 --> 
	   <view class="setp_buy_box" v-if="is_show_buy_box">
		    
		   <image @click="close_buy_dialog" class="close_icon" src="/static/images/close_icon.png"></image>
		   
		   <!-- 商品信息 -->
			<view class="goods_item" style="padding: 0 24rpx;"> 
				<view class="goods_img_box">
					<image class="goods_img" src="https://zjzdd.oss-cn-beijing.aliyuncs.com/public/uploads/goods/1690452261_60148.jpg"></image>
				</view>	
				<view class="goods_info_box">
					<view class="goods_title dialog_goods_title">珠江原浆啤酒11°P听装980m*1/6[冰镇]</view>	
				    <view class="discount_box">
						<view class="vip_text"> vip </view>
						<view class="discount_text"> 8.6折</view>
					</view>
					 
					<view class="buy_info">
						<view class="price_box">
							<text class="price_icon">￥</text>
							<text class="price_text">6.00</text> 
							<text class="market_price_text">￥28.00</text> 
						</view> 
					</view>
					  
				</view>	
			</view>
			 
			<!-- 商品规格 -->
			<view class="goods_attr_box">
				
				<view class="goods_attr_spec">
					<view class="goods_attr_title">规格 </view>
					<view class="goods_attr_list">
						<view class="goods_attr_item active">
							<view class="goods_attr_item_title">500ml*6听</view>
							<view class="goods_attr_item_tip">预估￥7.98/听</view>  
						</view>
						<view class="goods_attr_item">
							<view class="goods_attr_item_title">500ml*6听</view>
							<view class="goods_attr_item_tip">预估￥7.98/听</view>  
						</view>
						<view class="goods_attr_item">
							<view class="goods_attr_item_title">500ml*6听</view>
							<view class="goods_attr_item_tip">预估￥7.98/听</view>  
						</view>
						<view class="goods_attr_item">
							<view class="goods_attr_item_title">500ml*6听</view>
							<view class="goods_attr_item_tip">预估￥7.98/听</view>  
						</view>
					</view>
				</view>
				
				<view class="goods_attr_spec">
					<view class="goods_attr_title">规格 </view>
					<view class="goods_attr_list">
						<view class="goods_attr_item active">
							常温
						</view>
						<view class="goods_attr_item">
							冰镇
						</view>
						<view class="goods_attr_item">
							自定义请备注
						</view> 
					</view>
				</view>
				
				
				<view class="goods_numebr_box">
					<view class="goods_attr_title">数量 </view>
					<view class="goods_add_box">
						<image class="js_icon" src="/static/images/js_icon.png"></image>
						<input disabled value="1" type="text" class="goods_numebr_input">
						<image class="zj_icon" src="/static/images/zj_icon.png"></image>
					</view>
				</view>
				
				<button @click="buy_btn_click" class="coumon_btn">立即购买</button>
				 
			</view>
			
			 
	   </view>
	   
	   <!-- 确认订单的弹窗 -->
	   <view class="confrim_order_box" v-if="is_show_confir_order_box" >
			<image @click="close_confrim_order_dialog" class="close_icon" src="/static/images/close_icon.png"></image>
			<view class="confrim_order_title"> 确认订单 </view>
			<view class="confrim_order_tip">  现在下单，预计 <text>11:40</text>前送达 </view>
			
			<!-- 地址信息 -->
			<view class="address_box common_padding">
				
				<!-- 未添加地址样式 -->
				<view class="address_empty ">
					<view class="address_empty_tip">请选择配送地址</view>
					<image class="address_right_icon" src="/static/images/yellow-right-icon.png"></image> 
				</view>
				
				<!-- 选中后的地址 -->
				<!-- <view class="select_address_box"> 
					<view class="select_address_top">
						<view class="select_address_text">安徽省芜湖市繁昌县孙村镇4幢235室</view>
						<image class="black_right_icon" src="/static/images/black_right_icon.png"></image> 
					</view>
					<view class="select_address_bottom">
						<text>李豫卓</text>  
						<text>先生</text>  
						<text>13442197054</text>  
					</view>	 
				</view> -->
				
			</view>
			
			<!-- 商品信息 优惠券信息 提交订单按钮-->
			<view class="goods_content_box common_padding">
				<!-- 商品信息 -->
				<view class="goods_item" style="padding: 0 24rpx;"> 
					<view class="goods_img_box">
						<image class="goods_img" src="https://zjzdd.oss-cn-beijing.aliyuncs.com/public/uploads/goods/1690452261_60148.jpg"></image>
					</view>	
					<view class="goods_info_box">
						<view class="goods_title confrim_goods_title">珠江原浆啤酒11°P听装980m*1/6[冰镇]</view>	
						
						<view class="confrim_goods_spec">
							500ml*1听，冰镇
						</view>
						
						<view class="confrim_goods_number_price">
							 <view class="confrim_goods_number_price">
								 x2
							 </view>
							 <view class="buy_info">
								<view class="price_box">
									<text class="market_price_text">￥28.00</text> 
									<text class="price_icon confrim_price_icon">￥</text>
									<text class="price_text confrim_price_text">38.42</text>  
								</view> 
							 </view>
						</view>
						
						<view class="tip_price">
							约￥19.21/听
						</view>
						 
					</view>	
					
				</view>
				
				<!-- 优惠券选择 -->
			   <view class="coupon_box common_padding">
					<view class="coupon_text">优惠卷 </view>
					<view class="coupon_right_box"> 
						<view class="coupon_lable"> 3张优惠卷可用 </view>
						<!-- <view class="coupon_price_text"> -￥10 </view> -->
						<image class="gree_right_icon" src="/static/images/gree_right_icon.png"></image>
					</view>  
				</view>  
				  
			</view> 
			
			<!-- 提交订单信息 -->
			<view class="order_price_box">
				<view class="order_left_box">
					<view class="pay_price_box">
						<text class="pay_price_text">应付：</text>
						<text class="pay_price_icon">￥</text>
						<text>28.42</text>
					</view>
					<view class="youhui_price"> 已优惠￥1.58 </view>
				</view>
				<view class="order_right_box">
					<button @click="confrim_btn_click" class="coumon_btn">提交订单</button>
				</view>
			</view>	 
			
	  
	   </view>
	   
	   
	</view>
</template>

<script>
	export default {
		data() {
			return {
				cate_list:[],  // 一级分类列表
				cate_one_index:0, // 一级分类索引
				scrollInex:'scrollInex0',
				
				sort_list:['默认','销量','价格','筛选'],
				sort_index:0, // 排序索引
				
				scrollId:'scrollId0',
				cate_two_list:[],  // 一级分类列表
				cate_two_index:0, // 二级分类索引 
				dialog_screen_box:false,  // 是否显示 筛选菜单弹窗
				is_show_dialog: false,    // 是否显示 mask 
				is_show_buy_box:false,    // 是否显示商品弹窗
				is_show_confir_order_box:false,    // 是否显示商品弹窗
			}
		},
		onLoad() { 
			for(let i=1;i<20;i++){
				this.cate_list.push({
					name:'热门推荐' + i,
					id:i
				})
			}
			
			this.cate_two_list.push({
				name:'全部',
				id:0
			})
			for(let i=1;i<20;i++){
				this.cate_two_list.push({
					name:'五粮液' + i,
					id:i
				})
			}
			 
		},
		methods: {
			// 打开商品弹窗
			open_buy_dialog(){
				this.is_show_dialog = true
				this.is_show_buy_box = true
			},
			
			// 关闭商品弹窗
			close_buy_dialog(){
				this.is_show_dialog = false
				this.is_show_buy_box = false
			},
			
			// 关闭确认订单弹窗
			close_confrim_order_dialog(){
				this.is_show_dialog = false
				this.is_show_confir_order_box = false
			},
			  
			// 点击购买
			buy_btn_click(){
				
				// 关闭商品弹窗
				this.is_show_buy_box = false 
				// 显示确认订单弹窗
				this.is_show_confir_order_box = true 
			},
			
			// 确定购买
			confrim_btn_click(){
				this.is_show_dialog = false
				this.is_show_confir_order_box = false
			},

			// 一级分类点击切换
			change_one_index(index){
				if(this.cate_one_index != index){
					console.log('一级分类索引',index)
					this.cate_one_index = index 
					this.scrollInex = 'scrollInex' + index
				}
			},
			
			// 切换排序
			change_sort_index(index){
				
				this.sort_index = index  
				 
				// 展示筛选弹窗
				if(index === 3){
					this.dialog_screen_box = true
				}
			
			},
			
			// 切换二级分类的索引
			change_nav(index){
				if(this.cate_two_index != index){
					console.log('切换二级分类的索引',index)
					this.cate_two_index = index
					this.scrollId = 'scrollId' + index
				}
				
			},	
			
			
		}
	}
</script>

<style>
	
	.common_padding {
		padding: 0 24rpx;
	}
	
	.confrim_order_box .order_price_box {
		display: flex;
		align-items: center;
		justify-content: space-between;
		margin-top: 300rpx;
		background: #FFFFFF;
		box-shadow: 0rpx -6rpx 12rpx 0rpx rgba(193,193,193,0.3);
		padding: 32rpx ;
	}
	
	.confrim_order_box .order_price_box  .pay_price_box{
		font-size: 36rpx;
		font-family: Source Han Sans CN-Medium, Source Han Sans CN;
		font-weight: 600;
		color: #FF3243;
	}
	
	.confrim_order_box .order_price_box  .pay_price_box .pay_price_text {
		font-size: 28rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #666666;
	}
	
	.confrim_order_box .order_price_box  .pay_price_box .pay_price_icon {
		font-size: 28rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #FF3243;
	}
	
		
	.confrim_order_box .order_price_box   .youhui_price {
		font-size: 24rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #999999;
		margin-top: 10rpx;
	}
	
	.confrim_order_box .coupon_box{
		border-top: 2rpx solid #ECECEC;
		padding-top: 24rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	 
	.confrim_order_box .coupon_text {
		font-size: 28rpx;
		font-family: Source Han Sans CN-Medium, Source Han Sans CN;
		font-weight: 600;
		color: #666666;
	}
	
	.confrim_order_box .coupon_right_box {
		display: flex;
		align-items: center;
	}
		
	.confrim_order_box .coupon_right_box .coupon_lable {
		font-size: 24rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #FFFFFF;
		padding: 6rpx 10rpx ;
		background: #FF4B38;
		border-radius: 8rpx 8rpx 8rpx 8rpx;
	}
	
		
	.confrim_order_box .coupon_right_box  .coupon_price_text {
		font-size: 28rpx;
		font-family: Source Han Sans CN-Medium, Source Han Sans CN;
		font-weight: 600;
		color: #FF3243;
	}
	
	.confrim_order_box .coupon_right_box .gree_right_icon {
		width: 16rpx;
		height: 16rpx;
		margin-left: 16rpx;
	}
	
	 
	
	.confrim_order_box .confrim_order_title {
		font-size: 32rpx;
		font-family: Source Han Sans CN-Medium, Source Han Sans CN;
		font-weight: 600;
		color: #333333;
		text-align: center;
		padding-top: 10rpx;
	}
	
		
	.confrim_order_box .confrim_order_tip {
		margin-top: 48rpx;
		font-size: 32rpx;
		font-family: Source Han Sans CN-Medium, Source Han Sans CN;
		font-weight: 600;
		color: #333333;
		padding: 0 24rpx;
		margin-bottom: 20rpx;
	}
	
	.confrim_order_box .confrim_order_tip text {
		color: #FF7200;
		margin: 0 10rpx;
	}
	
		
	.confrim_order_box  .address_empty {
		line-height: 76rpx;
		background: #F7FAFF;
		border-radius: 16rpx 16rpx 16rpx 16rpx;
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 0 28rpx;
		margin-bottom: 24rpx;
	}
	
	.confrim_order_box  .address_empty .address_empty_tip {
		font-size: 28rpx;
		font-family: Source Han Sans CN-Medium, Source Han Sans CN;
		font-weight: 600;
		color: #FF7200;
	}
	 
	.confrim_order_box  .address_empty  .address_right_icon{
		width: 16rpx;
		height: 16rpx;
	}
	
		
	.confrim_order_box   .select_address_box {
		background: #F7FAFF;
		border-radius: 16rpx 16rpx 16rpx 16rpx;
		padding: 0 28rpx;
		margin-bottom: 24rpx;
	}
	
		
	.confrim_order_box   .select_address_box  .select_address_top {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	
		
	.confrim_order_box   .select_address_box  .select_address_text {
		font-size: 28rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #333333;
	}
	
	.confrim_order_box   .select_address_box .black_right_icon{
		width: 16rpx;
		height: 16rpx;
	}
	 
	.confrim_order_box   .select_address_box .select_address_bottom {
		margin-top: 10rpx;
		font-size: 24rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #999999;
	}
	
	.confrim_order_box   .select_address_box .select_address_bottom text:nth-of-type(2){
		margin: 0 10rpx;
	}
	
	
	.confrim_order_box  .goods_content_box {
		border-top: 20rpx solid #F7FAFF;
		padding-top: 24rpx;
	}
	
	.confrim_order_box  .goods_content_box  .confrim_goods_title { 
		width: 85%;
		white-space: nowrap;
		overflow: hidden;
		text-overflow: ellipsis;
	}
	
		
	.confrim_order_box  .goods_content_box  .confrim_goods_spec {
		font-size: 24rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #666666;
		margin-top: 20rpx;
	}
	
	.confrim_order_box  .goods_content_box .confrim_goods_number_price {
		display: flex;
		justify-content: space-between;
		padding-right: 40rpx;
		margin-top: 10rpx;
	}
	
	.confrim_order_box  .goods_content_box  .confrim_price_text {
		font-size: 32rpx;
		font-family: Source Han Sans CN-Medium, Source Han Sans CN;
		font-weight: 600;
		color: #333333 !important;
	}
	
	.confrim_order_box  .goods_content_box  .confrim_price_icon {
		color: #333333 !important;
	}
	
	.confrim_order_box  .goods_content_box  .tip_price {
		font-size: 24rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 600;
		color: #FF3243;
		text-align: right;
		padding-right: 38rpx;
	}
	
	
	
	.coumon_btn {
		width: 100%;
		line-height: 80rpx;
		background: linear-gradient(180deg, #FFA828 0%, #FF7603 100%);
		border-radius: 16rpx 16rpx 16rpx 16rpx;
		font-size: 28rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #FFFFFF;
	}
	
	
	.goods_attr_box {
		border-top: 20rpx solid #F7FAFF;
		padding:  24rpx;
	}
	
	.goods_numebr_box {
		display: flex;
		align-items: center;
		justify-content: space-between;
		margin: 30rpx 0;
	}
	
	.goods_add_box {
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	
	 .goods_add_box  .js_icon,
	 .goods_add_box  .zj_icon{
		width: 38rpx;
		height: 38rpx;
	}
	 
	.goods_add_box .goods_numebr_input {
		width: 100rpx;
		text-align: center;
	}
		
	 .goods_attr_title {
		font-size: 28rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #666666;
		margin-bottom: 16rpx;
	}
	
	
		
	.goods_attr_box  .goods_attr_list {
		display: flex;
		flex-wrap: wrap;
	}
	
		
	.goods_attr_box  .goods_attr_list  .goods_attr_item{
		width: 30%;
		margin-right: 3%;
		background: #F9F9F9;
		border-radius: 16rpx 16rpx 16rpx 16rpx;
		padding:  26rpx 0;
		word-break: break-all;
		margin-bottom: 24rpx;
		font-size: 28rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #333333;
		text-align: center;
		box-sizing: border-box;
	} 
	
	.goods_attr_box  .goods_attr_list  .goods_attr_item.active {
		background: #FFE6D2;
		border-radius: 16rpx 16rpx 16rpx 16rpx; 
		border: 2rpx solid #FF7200;
		font-weight: bold;
	}
	 
	.goods_attr_box  .goods_attr_list  .goods_attr_item .goods_attr_item_title{
		font-size: 28rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		color: #333333;
		margin-bottom: 10rpx;
	}
	
	.goods_attr_box  .goods_attr_list  .goods_attr_item .goods_attr_item_tip{
		font-size: 24rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		color: #333333;
	}
	 
	.goods_attr_box  .goods_attr_list  .goods_attr_item:nth-of-type(3n){
		margin-right: 0;
	}
	
		
	.dialog_fixed_box {
		position: fixed;
		z-index: 100;
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
		background: rgba(0,0,0,.4);
	}
	
		
	.setp_buy_box,
	.confrim_order_box {
		position: fixed;
		z-index: 101;
		background: #fff; 
		left: 0;
		right: 0;
		bottom: 0;
		padding: 24rpx 0 10rpx ;  
		border-radius: 30rpx 30rpx 0 0 ;
		transition: all .3s;  
	}
	
	.height_clear{
		height: auto;
	}
	
	.close_icon {
		width: 32rpx;
		height: 32rpx;
		position: absolute;
		top: 32rpx;
		right:32rpx;
	}
	
	.dialog_goods_title {
		padding-right: 50rpx;
	}
	
	.dialog_fixed {
		position: absolute;
		z-index: 100;
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
		background: rgba(0,0,0,.4);
	}
	
	.screen_box {
		background: #F7FAFF;
		border-radius: 0 0 30rpx 30rpx;
		height: 100%;
		margin-top: -140rpx;
		padding: 16rpx 24rpx ;
		overflow: hidden;
	}
	
	.screen_top_box {
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-bottom: 16rpx;
	}
	
	.screen_top_box .screen_top_cate_text {
		flex: 1;
		font-size: 32rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #666666;
	}
	
	.screen_top_box .screen_top_up_text {
		width: 20px;
		font-size: 24rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #333333;
		text-align: center;
	}
	
	.screen_top_box .screen_top_up_text .up_icon{
		width: 16px;
		height: 12rpx;
	}
	
	
	.screen_cate_box {
		height: 100%;
		overflow-y: auto;
	}
	
	.screen_cate_list {
		padding-bottom: 120rpx;
	}
		
	.screen_cate_item {
		display: flex;
		background: #FFFFFF;
		border-radius: 16rpx 16rpx 16rpx 16rpx;
		padding: 12rpx 22rpx;
		margin-bottom: 10rpx;
	}
	
	.screen_cate_item  .screen_cate_left { 
		flex-shrink: 0;
		margin-right: 42rpx;
		width: 120rpx;
		text-align: center;
	}
	.screen_cate_item  .screen_cate_left .goods_img {
		width: 84rpx;
		height: 84rpx;
		border-radius: 16rpx 16rpx 16rpx 16rpx;
	}
	
	
		
	.screen_cate_item  .screen_cate_left .screen_cate_left_title {
		font-size: 24rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #666666;
		margin-top: 10rpx;
	}
	
	
	.screen_cate_item  .screen_cate_left.active .goods_img{
		border: 2rpx solid #FF7200;
	}
	 
	.screen_cate_item  .screen_cate_left.active .screen_cate_left_title{
		background: #FF7200;
		color: #FFFFFF;
		border-radius: 52rpx 52rpx 52rpx 52rpx;
		padding: 4rpx 8rpx;
	}
		
	.screen_cate_item  .screen_cate_right {
		display: flex;
		flex-wrap: wrap;
	}
	
	.screen_cate_item  .screen_cate_right  .screen_cate_right_item{
		line-height: 48rpx;
		background: #F7F7F7;
		border-radius: 120rpx 120rpx 120rpx 120rpx;
		padding: 0 24rpx;
		margin-bottom: 24rpx;
		font-size: 24rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #666666;
		margin-right: 24rpx;
	}
	
	.screen_cate_item  .screen_cate_right  .screen_cate_right_item:nth-of-type(3n){
		margin-right: 0;
	}
	
	.screen_cate_item  .screen_cate_right  .screen_cate_right_item.active {
		background: #FFE6D2;
		font-weight: 600;
		color: #FF7200;
	}
	
	
	.buy_info {
		display: flex;
		justify-content: space-between;
	}
	
	.buy_info .buy_btn{
		width: 88rpx;
		line-height: 52rpx;
		background: #FFE500 linear-gradient(180deg, #FFA828 0%, #FF7603 100%);
		border-radius: 8rpx 8rpx 8rpx 8rpx;
		font-size: 24rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #FFFFFF;
		border:none;
		padding: 0;
	}
	
		
	.buy_info .price_box .price_icon{
		font-size: 20rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #FF3243;
	}
	
	.buy_info .price_box .price_text {
		font-size: 32rpx;
		font-family: Source Han Sans CN-Medium, Source Han Sans CN;
		font-weight: 600;
		color: #FF3243;
	}
	
	
	.buy_info .price_box .price_tip_text {
		font-size: 20rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #FF3243;
	}
	
	.buy_info .price_box .market_price_text {
		font-size: 20rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #999999;
		text-decoration: line-through;
	}
	
	.new_tag_wapper {
		display: flex; 
		margin-bottom: 15rpx;
	}
	
	.new_tag_box {
		display: flex;
		align-items: center; 
		margin-right: 8rpx;
	}
	
	.new_tag_box .new_text{  
		background: linear-gradient(220deg, #FE3516 0%, #FBA394 100%);
		font-size: 20rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #FFFFFF; 
		border-radius: 4rpx 0rpx  0rpx  4rpx;  
		text-align: center;
		line-height: 40rpx;
		padding: 0 2rpx;
	}
	
	.new_tag_box .new_tag_text { 
		background: #FAE9E5;
		border-radius: 0rpx 4rpx 4rpx 0rpx;
		font-size: 20rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #FE391B;
		padding: 0 2rpx;
		line-height: 40rpx;
	}
	
	
	.discount_box {
		display: flex;
		align-items: center; 
		font-size: 20rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #FFFFFF;
		margin-bottom: 16rpx;
	}
	
	.discount_box .vip_text {
		width: 56rpx;
		line-height: 40rpx;
		background: linear-gradient(250deg, #282828 0%, #9D9D9D 100%);	
		text-align: center;
		border-radius: 4rpx 0rpx  0rpx  4rpx;
	}
	
	.discount_box .discount_text {
		line-height:40rpx; 
		background: #FE391B;
		border-radius: 0rpx 4rpx 4rpx 0rpx;
		padding: 0 20rpx;
	}
	
	 
	.goods_item {
		display: flex;
		margin-bottom: 38rpx; 
	}
	
	.goods_item  .goods_img_box {
		width: 180rpx;
		height: 180rpx;
		border-radius: 16rpx 16rpx 16rpx 16rpx; 
		border: 2rpx solid #ECECEC;	
		flex-shrink: 0;
		margin-right: 16rpx; 
	}
	
	.goods_item  .goods_img_box .goods_img {
		width: 100%;
		height: 100%;
		border-radius: 16rpx 16rpx 16rpx 16rpx; 
	}
	
	.goods_item .goods_info_box {
		padding: 10rpx 0;
	}
	
	.goods_item .goods_info_box  .goods_title{
		font-size: 28rpx;
		font-family: Source Han Sans CN-Medium, Source Han Sans CN;
		font-weight: 600;
		color: #333333;
		line-height: 33rpx;
		margin-bottom: 12rpx;
		word-break: break-all;
	}
	
	.goods_label_box {
		display: flex;
		align-items: center;
		margin-bottom:14rpx;
	}
	
	.goods_label_box .label_one_text {
		font-size: 24rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #338DEE;
		margin-right: 10rpx;
	}
	
	.goods_label_box .label_two_text {
		font-size: 24rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #666666;
	}
	
	
	.tite_box {
		line-height: 88rpx;
		background: #F7FAFF;
		text-align: center;
		font-size: 36rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #333333;
	}
	
	.content {
		display: flex;
		flex-direction: column;
		height: 100vh;
	}
	
	.goods_box {
		 flex: 1;
		 height: 45vh;
	}
	
	.goods_box  .goods_list {
		height: 100%;
	}
	
	.goods_bottom {
		height: 100rpx;
	}
	 
	.sort_row_box {  
		padding-bottom: 20rpx;
	}
	
	.sort_row_list {
		width: 100%;
		height: 48rpx;
		white-space: nowrap; 
	}
	
	.sort_row_list .cate_two_item{
		display: inline-flex ;
		margin-right:14rpx;
		position: relative; 
		font-size: 24rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #666666;
		background: #F7F7F7;
		border-radius: 120rpx;
		padding: 0 24rpx ;
		line-height: 48rpx;
	}
	
	.sort_row_list .cate_two_item:last-child{
		margin-right:0;
	}
	
	.sort_row_list .cate_two_item.active{
		font-weight: 600;
		color:#FF7200;
		background: #FFE6D2; 
	}
	
	.sort_list_box { 
		margin: 8rpx 0;
		padding: 24rpx 0;
		display: flex;
		justify-content: space-between;
		align-items: center;
		box-sizing: border-box;
		text-align: center;
	}
		
	.sort_list_box  .sort_item {
		font-size: 24rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #666666;
		width: 25%;
	}
	
	.sort_list_box  .sort_item.active{
		font-weight: 600;
		color: #333333;
	}
	
	.swiper {
		width: 100%;
		height: 188rpx;
		border-radius: 16rpx; 
	}
	.swiper-item,
	.swiper_item_img{
		width: 100%;
		height: 188rpx;
		border-radius: 16rpx;
	}
		
	.main_inner_box {
		display: flex; 
		height: 100%; 
	}
	
	/* 左侧菜单样式开始 */
	.main_left_box{
		/* width: 176rpx; */
		width: 25%; 
		background-color:#F9F9F9;
		flex-shrink: 0;
	}
	
	
	.main_left_box  .menu_list {
		height: 71.5vh;  
	}
	 
	.main_left_box  .menu_list .menu_bottom {
		height: 100rpx;
	}
		 
	.main_left_box .menu_item {
		line-height: 84rpx;
		text-align: center;
		font-size: 24rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		font-weight: 400;
		color: #666666;
	}
	
	.main_left_box .menu_item.active {
		font-weight: 600;
		color: #333333;
		background: #fff;
	}
	
	.main_left_box .menu_item.active::before{
		content: '';
		display: inline-block;
		width: 6rpx;
		height: 16rpx;
		background: #FFE500;
		border-radius:  36rpx;
		position: relative;
		left: -16rpx;
	}
	
	/* 左侧菜单样式结束 */
	
	.main_right_box {
		flex: 1;  
		width: 75%;
		padding-left: 16rpx; 
		padding-right: 24rpx;
		box-sizing: border-box;
		display: flex;
		flex-direction: column;
		height: 71.5vh;
		overflow: hidden;
	}
	  
	
	.header_box { 
		background: #F7FAFF;
		padding-bottom: 36rpx;
	}
	
	.ad_box {
		width: 100%;
		height: 98rpx;
		position: relative;
	}
	
	.ad_box .ad_img   { 
		width: 476rpx;
		height: 98rpx;
	}
	
	.ad_box  .ad_text{ 
		font-size: 24rpx;
		font-family: Source Han Sans-Regular, Source Han Sans;
		color: #333333;
		position: absolute;
		right: 58rpx;
		bottom: 18rpx; 
	}
	
	.ad_box  .ad_text::before{
		content: '';
		display: inline-block;
		width: 10rpx;
		height: 10rpx;
		background: #FF7200;
		border-radius: 50%;
		margin-right:8rpx ;
	}
	
	.search_box {
		padding: 24rpx 0 24rpx 40rpx ;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	
	.search_box .input_box{ 
		border-radius: 20rpx; 
		border: 2rpx solid #FF7200;	 
		padding: 18rpx 32rpx;
		display: flex;
		align-items: center;
		justify-content: space-between; 
		margin-right: 10rpx;
		flex: 1;
	}	
	
	.search_box .input_box .search_icon {
		width: 40rpx;
		height: 40rpx;
		margin-right: 8rpx;
	}
	
	.search_box .input_box .input {
		height: 100%;
		width: 100%;
	}
	
	.search_box .coupon_box {
		width:  156rpx;
		height: 64rpx; 
		display: flex;
		align-items: center;
		justify-content: space-between;
		background: url('../../static/images/coupon_bg.png') no-repeat;
		background-size: 100% 100%;
		padding:  0 24rpx; 
		box-sizing: border-box;
	}
	
	.search_box .coupon_box  .coupon_icon {
		width: 32rpx;
		height: 32rpx; 
	}
	
	.search_box .coupon_box  .coupon_right_icon {
		width: 18rpx;
		height: 18rpx; 
	}
	.search_box .coupon_box  .coupon_text {
		font-size: 24rpx;
		font-family: Source Han Sans CN-Regular, Source Han Sans CN;
		color: #FFFFFF;
	}
	
	 
	.main_box { 
		flex: 1;
		padding-top: 24rpx;
		position: relative;
	}
	 
	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
	 
</style>
