<h1 align="center"> 天气查询 </h1>



## 安装

```shell
$ composer require boringiii/weather -vvv
```

## 使用
PS: 需申请高德开发平台应用 API KEY（反正是免费的）
```php
require __DIR__ .'/vendor/autoload.php';

use Boringiii\Weather\Weather;

// 高德开放平台应用 API Key
$key = 'bb5e3bd493d1f29f52f9d8ee4bf47049';
$w = new Weather($key);

echo "获取实时天气：\n";

$response = $w->getWeather('深圳');
echo json_encode($response, JSON_UNESCAPED_UNICODE | JSON_PRETTY_PRINT);

echo "\n\n获取天气预报：\n";

$response = $w->getWeather('深圳', 'all');
echo json_encode($response, JSON_UNESCAPED_UNICODE | JSON_PRETTY_PRINT);

echo "\n\n获取实时天气(XML)：\n";

echo $w->getWeather('深圳', 'base', 'XML');
```

## 正常响应
```angular2html
获取实时天气：
{
    "status": "1",
    "count": "1",
    "info": "OK",
    "infocode": "10000",
    "lives": [
        {
            "province": "广东",
            "city": "深圳市",
            "adcode": "440300",
            "weather": "中雨",
            "temperature": "27",
            "winddirection": "南",
            "windpower": "6",
            "humidity": "94",
            "reporttime": "2018-08-21 16:00:00"
        }
    ]
}

获取天气预报：
{
    "status": "1",
    "count": "1",
    "info": "OK",
    "infocode": "10000",
    "forecasts": [
        {
            "city": "深圳市",
            "adcode": "440300",
            "province": "广东",
            "reporttime": "2018-08-21 11:00:00",
            "casts": [
                {
                    "date": "2018-08-21",
                    "week": "2",
                    "dayweather": "雷阵雨",
                    "nightweather": "雷阵雨",
                    "daytemp": "31",
                    "nighttemp": "26",
                    "daywind": "无风向",
                    "nightwind": "无风向",
                    "daypower": "≤3",
                    "nightpower": "≤3"
                },
                {
                    "date": "2018-08-22",
                    "week": "3",
                    "dayweather": "雷阵雨",
                    "nightweather": "雷阵雨",
                    "daytemp": "32",
                    "nighttemp": "27",
                    "daywind": "无风向",
                    "nightwind": "无风向",
                    "daypower": "≤3",
                    "nightpower": "≤3"
                },
                {
                    "date": "2018-08-23",
                    "week": "4",
                    "dayweather": "雷阵雨",
                    "nightweather": "雷阵雨",
                    "daytemp": "32",
                    "nighttemp": "26",
                    "daywind": "无风向",
                    "nightwind": "无风向",
                    "daypower": "≤3",
                    "nightpower": "≤3"
                },
                {
                    "date": "2018-08-24",
                    "week": "5",
                    "dayweather": "雷阵雨",
                    "nightweather": "雷阵雨",
                    "daytemp": "31",
                    "nighttemp": "26",
                    "daywind": "无风向",
                    "nightwind": "无风向",
                    "daypower": "≤3",
                    "nightpower": "≤3"
                }
            ]
        }
    ]
}

获取实时天气(XML)：
<?xml version="1.0" encoding="UTF-8"?>
<response>
    <status>1</status>
    <count>1</count>
    <info>OK</info>
    <infocode>10000</infocode>
    <lives type="list">
        <live>
            <province>广东</province>
            <city>深圳市</city>
            <adcode>440300</adcode>
            <weather>中雨</weather>
            <temperature>27</temperature>
            <winddirection>南</winddirection>
            <windpower>6</windpower>
            <humidity>94</humidity>
            <reporttime>2018-08-21 16:00:00</reporttime>
        </live>
    </lives>
</response>⏎
```

## License

MIT
