---
title: "방법: PropertyNameChanged 패턴 적용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "사용자 지정 컨트롤[Windows Forms], 속성 변경(코드 사용)"
  - "데이터 바인딩, 사용자 지정 컨트롤"
  - "PropertyNameChanged 패턴, 적용"
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: PropertyNameChanged 패턴 적용
다음 코드 예제에서는 *PropertyName*Changed 패턴을 사용자 지정 컨트롤에 적용하는 방법을 보여 줍니다.  이 패턴은 Windows Forms 데이터 바인딩 엔진과 함께 사용되는 사용자 지정 컨트롤을 구현하려는 경우에 적용합니다.  
  
## 예제  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## 코드 컴파일  
 위의 코드 예제를 컴파일하려면  
  
-   코드를 빈 코드 파일에 붙여넣습니다.  이 사용자 지정 컨트롤은 `Main` 메서드가 포함된 Windows Form에 사용해야 합니다.  
  
## 참고 항목  
 [방법: INotifyPropertyChanged 인터페이스 구현](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)   
 [Windows Forms 데이터 바인딩의 변경 알림](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)   
 [Windows Forms 데이터 바인딩](../../../docs/framework/winforms/windows-forms-data-binding.md)