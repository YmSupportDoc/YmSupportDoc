## CPS 对接说明

&emsp;&emsp;目前Yeahmobi支持s2s的CPS对接方式，根据不同的分成模式，提供如下两种对接方式：

### 回传订单金额模式

&emsp;&emsp;适用于针对产品的收益分成是固定比例，在Yeahmobi后台配置好以后，当广告主端有交易发生时，发起一次http请求调用以下url并传入订单金额，Yeahmobi会自行计算应得收益。

URL: <http://yeahmobi-postback-domain/mconv?transaction_id={transaction_id}&event=purchase&order_id={order_id}&order_amount={order_amount}&external_id={external_id}&source={souce_name}>

**注：以下参数均为必须项。**

参数|说明
--|--
transaction_id|Yeahmobi生成的唯一识别码，点击时带入，回调时需要返回
order_id|订单的id，同一点击产生转化的order_id应一致order_amount|订单的金额，Yeahmobi会自行计算应得收益，格式为数字，默认货币单位为美元。例如order_amount=100，后台配置的分成比例为20%，则Yeahmobi收到后会自行计算应得收益为100*20%。
external_id|交易的唯一识别id，每一次请求的external_id应具有唯一性，由广告主提供
source|广告主标记，广告主自行配置，一般为广告主名称，主要用于调试和查错内部使用

### 回传收益模式

&emsp;&emsp;适用于产品有不固定的收益分成，或者针对产品的分成不是比例，是固定的金额。当广告主端有交易发生时，发起一次http请求调用以下url并直接传入Yeahmobi应得收益。

URL: <http://yeahmobi-postback-domain/mconv?transaction_id={transaction_id}&event=purchase&revenue={revenue}&external_id={external_id}&source={souce_name}> 

**注：以下参数均为必须项。**

参数	|说明
--|--
transaction_id|Yeahmobi生成的唯一识别码，点击时带入，回调时需要返回
revenue|订单的Yeahmobi应得收益，格式为数字，默认货币单位是美元。例如revenue=100，Yeahmobi收到后会认为应得收益为100。
external_id|交易的唯一识别id，每一次请求的external_id应具有唯一性，由广告主提供
source|广告主标记，广告主自行配置，一般为广告主名称，主要用于调试和查错内部使用

**说明：文档中的回调地址格式均真实有效，但域名yeahmobi-postback-domain仅为示例，需要对接的客户请联系客户经理获取真实回调域名。**