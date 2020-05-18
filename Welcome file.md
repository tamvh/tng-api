---


---

<h1 id="store">Store</h1>
<p>Get list store</p>
<ul>
<li>path: /api/v1/store/list</li>
<li>method: GET</li>
<li>param:</li>
</ul>
<pre><code>	- merchant_code
</code></pre>
<ul>
<li>response sample</li>
</ul>
<pre><code>[
  {
    "merchant_code": "HLC00001",
    "name": "Highlands Sala 2",
    "hotline": "+84382051088",
    "photos": "https://example.com/web/statics/image.png"
    "address": "127-129 Nguyễn Cơ Thach",
    "status": 1, // 1(valid), 0(invalid)
    "service_hours":
    {
	  "1": {
	    "opening_time": "08:00",
	    "closing_time": "22:00"
	  },
	  "2": {
	    "opening_time": "08:00",
	    "closing_time": "22:00"
	  },
	  "3": {
	    "opening_time": "08:00",
	    "closing_time": "22:00"
	  },
	  "4": {
	    "opening_time": "08:00",
	    "closing_time": "22:00"
	  },
	  "5": {
	    "opening_time": "08:00",
	    "closing_time": "22:00"
	  },
	  "6": {
	    "opening_time": "08:00",
	    "closing_time": "22:00"
	  },
	  "7": {
	    "opening_time": "08:00",
	    "closing_time": "22:00"
	  }
	},
    "latitude": 10.7704909,
    "longitude": 106.723932
  }
]
</code></pre>
<h1 id="category">CATEGORY</h1>
<p>Danh sách Category</p>
<ul>
<li>path: /api/v1/category/list</li>
<li>method: GET</li>
<li>param:</li>
</ul>
<pre><code>	 - merchant_code
	 - store_id
</code></pre>
<ul>
<li>response sample</li>
</ul>
<pre><code>[
  {
    "id": 1,
    "name": "quầy nước",
    "status" 1 // 1(valid), 0(invalid)
    "sequence": 1 // thứ tự sắp xếp
    "service_hours":
    {
	  "1": {
	    "opening_time": "08:00",
	    "closing_time": "22:00"
	  },
	  "2": {
	    "opening_time": "08:00",
	    "closing_time": "22:00"
	  },
	  "3": {
	    "opening_time": "08:00",
	    "closing_time": "22:00"
	  },
	  "4": {
	    "opening_time": "08:00",
	    "closing_time": "22:00"
	  },
	  "5": {
	    "opening_time": "08:00",
	    "closing_time": "22:00"
	  },
	  "6": {
	    "opening_time": "08:00",
	    "closing_time": "22:00"
	  },
	  "7": {
	    "opening_time": "08:00",
	    "closing_time": "22:00"
	  }
	 }
    }
  }
]
</code></pre>
<h1 id="menu">Menu</h1>
<p>Get list menu from partner</p>
<ul>
<li>path: /api/v1/item/list</li>
<li>method: GET</li>
<li>param:</li>
</ul>
<pre><code>  - merchant_code
  - store_id
</code></pre>
<ul>
<li>response sample</li>
</ul>
<pre><code>[
 {
  "id": 1,
  "code": "caphe",
  "name": "Cà phê đen",
  "name_en": "coffee",
  "store_id": 1,
  "category_id": 1,
  "type": 1, // 1(main), 2(toping)
  "original_price": 10000,
  "promotion_price": 1000,
  "price": 9000,
  "img_path": "",
  "status": 1(active), 0(inactive)
  "description": "",
  "sequence": 1 // thứ tự ưu tiên
  "quantity": 100,
  "group_variant":[
      "id": 1,
      "name": "Size",
      "name_en": "Size",
      "status": 1, 1(active), 0(inactive)
      "selection_range_max": 100, //giới hạn được chọn 1 lần
      "is_required": 1, 1(bắt buộc chọn 1), 0(có thể chọn hoặc không)
      "img":"",
      "variant": [
        {
          "id": 1,
          "name": "SizeS",
          "name_en": "SizeS"
          "status": 1, 1(active), 0(inactive)"
          "price": 1000,
          "quantity": 100,
          "img":"",
        },
        {
          "id": 2,
          "name": "SizeM",
          "name_en": "SizeM"
          "status": 1, 1(active), 0(inactive)"
          "price": 1000,
          "quantity": 100,
          "img":"",
        },
        {
          "id": 3,
          "name": "SizeL",
          "name_en": "SizeL"
          "status": 1, 1(active), 0(inactive)"
          "price": 1000,
          "quantity": 100,
          "img":"",
        }
      ],
      "toping":[
        {
          "id": 1,
          "code": "thach_cf",
          "name": "Thạch cà phê",
          "name_en": "",
          "store_id": 1,
          "category_id": 1,
          "type": 1, //1(món chính), 2(toping)
          "original_price": 10000,
          "promotion_price": 1000,
          "price": 9000,
          "img_path": "",
          "status": 1(active), 0(inactive)
          "description": "",
          "quantity": 100,
        }
      ]
    ]
  }   
]
</code></pre>
<h1 id="order">Order</h1>
<ol>
<li>Create Order</li>
</ol>
<ul>
<li>path: /api/v1/order/create</li>
<li>method: POST</li>
<li>body request</li>
</ul>
<pre><code>{
	"order_no":"200518000001" // đây là mã do zalopay gen
	"payment_code": "ZALOPAY" // ZALOPAY, COD
	"order_method": "PICKUP" // PICKUP, DELIVERY
	"delivery_code": "AHAMOVE" // đối tác delivery nếu có
	"amount": 30000
	"customer": {
		"name":"Tamvh",
		"phone": "0935954858",
		"email":"",
		"shipping_address": {
			"full_address":"182 Le Dai Hanh",
			"country": "VN",
			"province": "77",
			"district":"889",
			"ward":"1896",
			"lat":0.0,
			"long":0.0
		}
	},
	"items":[
		{
		  "id": 111,
		  "parner_id": 1, // item id của OngBau
		  "group_variant":[
		  	  "id":1,
		      "parner_id": 1, // group_variant id của OngBau
		      "variant": [
		        {
		          "id": 1,
		          "parner_id": 1, // variant id của OngBau
		          "quantity": 100
		        },
		        {
		          "id": 2,
		          "parner_id": 2,
		          "quantity": 100
		        },
		        {
		          "id": 3,
		          "parner_id": 3,
		          "quantity": 100
		        }
		      ],
		      "toping":[
		        {
		          "id": 4,
		          "parner_id": 4,
		          "quantity": 100
		        }
		      ]
		    ]
		  }
	]
}
</code></pre>
<ul>
<li>Response:</li>
</ul>
<pre><code>Success
{
	"code": 0,
	"data" &lt;mã đơn hàng của OngBau&gt;
}
Failed
{
	"code":  &lt;error_code&gt;,
	"message": &lt;error_message&gt;
}
</code></pre>
<ol start="2">
<li>Get status order from partner</li>
</ol>
<ul>
<li>path: /api/v1/order/status</li>
<li>method: GET</li>
<li>param:</li>
</ul>
<pre><code>	- order_no 
</code></pre>
<ul>
<li>response sample</li>
</ul>
<pre><code>Success
{
	"code": &lt;status của đơn hàng -&gt; sẽ định nghĩa sau&gt;,
}
Failed
{
	"code":  &lt;error_code&gt;,
	"message": &lt;error_message&gt;
}
</code></pre>
<h1 id="callback">CALLBACK</h1>
<p>Phía OngBau sẽ gọi cho zalopay nếu huỷ đơn hàng,…, cập nhật menu, cập nhật store, cập nhật category</p>
<ol>
<li>Update order</li>
</ol>
<ul>
<li>path: /api/v1/cb/order_status</li>
<li>method: GET</li>
<li>param:</li>
</ul>
<pre><code>	- order_no // order của zalopay
	- status // sẽ cập nhât bộ enum về trạng thái sau khi bàn bạc giữa các bên
</code></pre>
<ul>
<li>response sample</li>
</ul>
<pre><code>Success
{
	"code": 0,
	"data" "order_no" // order của zalopay
}
Failed
{
	"code":  &lt;error_code&gt;,
	"message": &lt;error_message&gt;
}
</code></pre>
<ol start="3">
<li>Update common</li>
</ol>
<ul>
<li>path: /api/v1/cb/update</li>
<li>method: GET</li>
<li>param:</li>
</ul>
<pre><code>	- update_type //UPDATE_MENU, UPDATE_STORE, UPDATE_CATEGORY
</code></pre>
<ul>
<li>response sample</li>
</ul>
<pre><code>Success
{
	"code": 0, // Đã nhận thông tin đơn hàng
}
Failed
{
	"code":  &lt;error_code&gt;,
	"message": &lt;error_message&gt;
}
</code></pre>
<h1 id="refund">Refund</h1>
<p>Bàn bạc với đối tác</p>
<h1 id="reconcile">Reconcile</h1>
<p>Bàn bạc với đối tác</p>

