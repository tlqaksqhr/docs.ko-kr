---
title: "XML에서 데이터 형식 클래스 생성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# XML에서 데이터 형식 클래스 생성
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에는 XML에서 데이터 형식 클래스를 생성하는 새 기능이 포함되어 있습니다.  이 항목에서는 MSDN 라이브러리 RSS 피드에 대한 데이터 형식을 자동으로 생성하는 방법에 대해 설명합니다.  
  
### MSDN 라이브러리 RSS 피드에서 XML 가져오기  
  
1.  Internet Explorer에서 [MSDN RSS 피드](http://go.microsoft.com/fwlink/?LinkId=225209)로 이동합니다.  
  
2.  페이지를 마우스 오른쪽 단추로 클릭하고 **소스 보기**를 선택합니다.  
  
3.  **Ctrl\+A**를 눌러 모든 텍스트를 선택한 다음 **Ctrl\+C**를 눌러 피드의 텍스트를 복사합니다.  
  
### 데이터 형식 만들기  
  
1.  프록시를 사용할 코드 파일을 엽니다.  이 파일은 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 프로젝트의 일부여야 합니다.  
  
2.  커서를 기존 클래스 외부에 있는 파일의 한 위치에 배치합니다.  
  
3.  **편집**, **선택하여 붙여넣기**, **XML을 클래스로 붙여넣기**를 선택합니다.  
  
4.  `rss`, `rssChannel`, `rssChannelImage` 및 `rssChannelItem`이라는 클래스는 RSS 피드의 요소에 액세스하는 데 필요한 멤버를 사용하여 만들어집니다.  
  
### 생성된 클래스 사용  
  
1.  생성된 클래스는 다른 클래스와 마찬가지로 코드에서 사용할 수 있습니다.  다음 코드 예제에서는 `rssChannelImage` 클래스의 새 인스턴스를 반환합니다.  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
  
    ```