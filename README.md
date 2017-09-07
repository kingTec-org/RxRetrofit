# RxRetrofit
基于Retrofit2.x和Rxjava2.x封装的请求工具类

## GET
```javascript
RetrofitClient.getInstance(context)
              .createBaseApi()
              .get("you path url"
                    ,maps, maps, new Subscriber<IpResult>());
```

## POST
```javascript
RetrofitClient.getInstance(context)
             .createBaseApi(
              ).post("you path url"
                    ,maps, maps, new Subscriber<IpResult>());
```

## JSON
```javascript
   RequestBody jsonbody = RequestBody.create(okhttp3.MediaType.parse("application/json; charset=utf-8"), new Gson().toJson(user));

     RetrofitClient.getInstance(MainActivity.this)
         .createBaseApi()
         .json("url", jsonBody, new BaseSubscriber<T>(context) {

  }
```

## UPLOAD
```javascript
  RequestBody requestFile =
                    RequestBody.create(MediaType.parse("image/jpg"), new File(mPath));
        
    RetrofitClient.getInstance(MainActivity.this)
              .createBaseApi()
               .upload(url, requestFile, new Subscriber<ResponseBody>);
```

## DOWNLOAD
```javascript
    RetrofitClient.getInstance(MainActivity.this)
                 .createBaseApi()
                    .download(url1, new CallBack());
```

## Execute you APIService
```javascript
    //create  you APiService    
     MyApiService service = RetrofitClient.getInstance(MainActivity.this).create(MyApiService.class);    
   // execute and add observable    
   RetrofitClient.getInstance(MainActivity.this).execute(            
                              service.getData("21.22.11.33"), new Subscriber<IpResult>() {                                     

             
               });}
```


