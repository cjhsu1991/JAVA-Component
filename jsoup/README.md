## Java 使用 Jsoup library 爬取網頁資料(使用 maven 管理 library 相關套件)
### Step 1: 在 pom.xml 中加入下載 jsoup 套件
```
<dependency>
    <groupId>org.jsoup</groupId>
    <artifactId>jsoup</artifactId>
    <version>1.14.1</version>
</dependency>
```

### Step 2: 新增一個 java file
```
    public static void main(String args[]) throws IOException {
	/**
        * 爬取某個網址的資料
        */
        Document doc = Jsoup.connect("你要爬取的網址").get();
        
        /**
        * 取得某段 script 中的資訊，以這段為例是取得 <script type="application/Id+json"></script> 的 html 原始碼
        */
        Elements scriptElements = doc.select("script[type=\"application/ld+json\"]");
        String scriptContent = scriptElements.first().html();

        /**
        * 輸出資料確認
        */
        System.out.println(scriptContent);
    }
```
