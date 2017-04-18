---
title: "공간 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 공간 함수
공간 형식의 경우 리터럴 형식이 없습니다.  그러나 WKT\(Well Known Text\) 형식의 문자열을 사용하여 호출하는 정식 Entity Framework 함수를 사용할 수 있습니다.  예를 들어 다음 함수 호출은 기하 도형 점을 만듭니다.  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 [SpatialEdmFunctions 메서드](http://msdn.microsoft.com/library/hh749531.aspx) 페이지에는 모든 공간 정식 Entity Framework 메서드가 나와 있습니다.  함수에 전달해야 하는 매개 변수를 보려면 해당 메서드를 클릭하세요.