Fecshop 优惠券
==================

> 通过后台设置优惠券，用户可以使用优惠卷码进行折扣，
> 目前fecshop的优惠券功能比较简单。

优惠券后台的添加
![xxxx](images/a41.jpg)

1.优惠卷码: 这个必须唯一

2.每个用户最大的使用次数：这个顾名思义，就是优惠券，每个用户最多使用多少次

3.类型：折扣的类型，是按照百分比的方式折扣，还是直接立减的方式折扣

4.金额>?才可使用：这个是使用优惠券的条件，当购物车金额满足多少的时候才可以使用优惠券

5.折扣，也就是减去的部分，如果折扣类型是百分比优惠， 那么填写10的意思是
减少产品总价的10%，如果是金额优惠，那么填写10的意思是
产品总价减少10。

6.过期时间，如果超过这个时间，优惠券则不可用。

后台设置后，就可以在前端使用了，目前优惠券没有做到和某个用户绑定，

现在的优惠券功能，更多的是为了给定量的客户发送邮件，刺激用户进行二次购买。

7.优惠券必须在用户登录状态下才能使用，在购物车页面进行使用的（必须满足优惠券
使用的条件，满足条件才可以使用），
使用后，购物车表中会记录该优惠券，优惠券的使用次数会被+1，在购物车
中的优惠券是可以取消的，
当用户生成订单后，购物车中的信息会被清空，包括优惠券，
至此，优惠券使用完成，即使订单没有支付，优惠券也会被记录使用次数+1.



















