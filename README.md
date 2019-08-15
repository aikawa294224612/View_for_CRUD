# View_for_CRUD
### 輸出類型為類別庫的專案無法直接起始 解決方法
[https://nobi-learning.blogspot.com/2018/03/vs-visual-studio-2017.html](https://nobi-learning.blogspot.com/2018/03/vs-visual-studio-2017.html)
在"專案"->"設定為啟始專案"，重新"開始偵錯(F5)"

### Area
[asp.net mvc設定area頁面為預設路由](https://www.itread01.com/content/1546171747.html)

    routes.MapRoute(
                    name: "Default",
                    url: "{controller}/{action}/{id}",
                    defaults: new { controller = "Home", action = "Index", id = UrlParameter.Optional },
                    namespaces:new string[]{"EFTest.Controllers"}
                ).DataTokens.Add("Area","Test");

[ASP.NET MVC 使用 Area - 以 Backend 後台為例](http://kevintsengtw.blogspot.com/2013/07/aspnet-mvc-area-backend.html)

### HtmlHelper.ActionLink
[從零開始的MVC開發-HtmlHelper.ActionLink以及button](https://ithelp.ithome.com.tw/articles/10188851)

    @Html.ActionLink("刪除","Index",new{id=item.id},new {@class="btn btn-default"})
分別是顯示文字,action,controller, 帶的參數, htmlAttributes
搭配上bootstrap,就從原本的超連結,變成button

### int? number;
是System.Nullable<T>的縮寫形式，表可為null

### Request.Form與Request.QueryString
[https://dotblogs.com.tw/topcat/2008/03/05/1200](https://dotblogs.com.tw/topcat/2008/03/05/1200)
當有資料要傳給某個asp來處理時，有幾個方式可以運作  
1.Session  
2.Form Submit  
3.QueryString

**Request.QueryString:**

    aaa.asp?a=123&b=456
 

    <%  
    a=Request.QueryString("a").Item  
    b=Request.QueryString("b").Item  
    c=Request.QueryString("c").Item  
    %>

**Request.Form:**

    <FORM action="aaa.asp" method=POST id=form1 name=form1>
    <INPUT type="text" id=text1 name=text1><br>
    <INPUT type="text" id=text2 name=text2><br>
    <INPUT type="submit" value="Submit" id=submit1 name=submit1>
    </FROM>
    
    <%
    text1=Request.Form("text1").Item
    text2=Request.Form("text2").Item
    %>

### jQuery ajax - serialize()

    <form>
      <div><input type="text" name="a" value="1" id="a" /></div>
      <div><input type="text" name="b" value="2" id="b" /></div>
      <div><input type="hidden" name="c" value="3" id="c" /></div>
      <div>
        <textarea name="d" rows="8" cols="40">4</textarea>
      </div>
      <div><select name="e">
        <option value="5" selected="selected">5</option>
        <option value="6">6</option>
        <option value="7">7</option>
      </select></div>
      <div>
        <input type="checkbox" name="f" value="8" id="f" />
      </div>
      <div>
        <input type="submit" name="g" value="Submit" id="g" />
      </div>
    </form>



    $('form').submit(function() {
      alert($(this).serialize());
      return false;
    });
    
    a=1&b=2&c=3&d=4&e=5
