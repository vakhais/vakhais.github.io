---
title:  "thymeleaf 이중 each"
excerpt: "thymeleaf 이중 each 샘플"
categories:
  - Develop
tags:
  - thymeleaf
---

thymeleaf는 해도해도 적응이 안된다..  
하지만 어쩌겠나...


```html
<tr th:each="data : ${noticeList}"> 
    <td ></td> 
    <td> 
        <a th:text="${data.notice_title}" th:href="@{/admin/noticeInfo(notice_seq=${data.notice_seq}notice_lang_code=${data.notice_lang_code})}"></a>
    </td> 
    <td th:text="${data.popup_yn}"></td> 
    <td> 
        <block th:each=" lang : ${#strings.arraySplit(data.save_lang,',')}" th:remove="tag"> 
            <img th:src="@{localhost:8080/} + ${lang}" width="20" height="20" th:alt="${lang}"/> 
        </block> 
    </td> 
    <td th:text="${data.reg_date}"></td> <td th:text="${data.notice_viewcnt}"></td> 
</tr>
```