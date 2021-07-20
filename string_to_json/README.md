## Java String to Json 

### Step 1 : 在 pom.xml 新增 json library 的 dependency

```
<dependency>
    <groupId>org.json</groupId>
    <artifactId>json</artifactId>
    <version>20210307</version>
</dependency>
```

### Step 2 : 新增 JSON FILE
```
import org.json.JSONArray;
import org.json.JSONException;
import org.json.JSONObject;
public static void main(String args[]) throws IOException {
    /**
    * 把字串內容轉成 JSONArray
    */
    JSONArray array = new JSONArray("字串內容");

    /**
    * 把字串內容轉成 JSONObject
    */
    JSONObject object = new JSONObject("字串內容");

    /**
    * 解析 JSONArray
    */
    for (int i = 0; i < array.length(); i++) {
        JSONObject object = obj.getJSONObject(i); # 取得第 i 個 JSONObject 內容
        String keyContent = object.get("輸入 key 值的內容"); # 取得 JSONObject key 值的內容
        System.out.println(keyContent); # 輸出 key 值的 value 進行確認
    }
}
```