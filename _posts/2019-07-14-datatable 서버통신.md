---
title:  "datatable 서버통신 샘플"
excerpt: "jquery datatable 서버통신 샘플"
categories:
  - Develop
tags:
  - javascript
  - jquery
---

관리자 bo 작업시 종종 datatable을 써야하는 경우가 있다.  
테이블 정렬 등의 요구사항이 있을시엔 datatable이 정말 편하다. 

[datatable 공식사이트](https://datatables.net/)

일반 렌더링 예제는 많이 있는데 server 렌더링은 예제가 많이 없는듯 하여  
샘플 코드를 남겨놓는다.  

```javascript 
$( document ).ready(function() { 
    
    var param = "?group_code=" + $('#group_code option:selected').val(); 
    
    param = encodeURI(param); 
    commonCodeDataTable = $('#datatable').DataTable({ 
        bFilter: false, 
        select: true, 
        "processing":true, 
        "serverSide":true, 
        "stateSave":true, 
        "ajax":{ 
            "url":"/admin/getCommonCodeJsonList" + param 
        }, 
        "columns": [ 
            {"data":"common_code"}, 
            {"data":"common_value"}, 
            {"data":"common_desc"}, 
            {"data":"common_seq"}, 
        ] 
    }); 
    commonCodeDataTable.column( 3 ).visible( false ); 
    
    $('#group_code').change(function(){ 
        var param = "?group_code="+$(this).val(); 
        param = encodeURI(param); 
        commonCodeDataTable.ajax.url("/admin/getCommonCodeJsonList"+param).load(); 
    }); 
});
```