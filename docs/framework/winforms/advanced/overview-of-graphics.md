---
title: "그래픽 개요 | Microsoft Docs"
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
  - "그래픽, 그래픽 정보"
  - "그래픽, 관리되는 인터페이스 사용"
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 그래픽 개요
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]는 Microsoft Windows 운영 체제의 하위 시스템을 구성하는 API\(응용 프로그래밍 인터페이스\)입니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]는 화면과 프린터에 정보를 표시합니다.  이름에서 알 수 있듯이, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]는 이전 버전의 Windows에 포함된 그래픽 장치 인터페이스인 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]의 후속 프로그램입니다.  
  
## 관리되는 클래스 인터페이스  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API는 관리 코드로 배포된 클래스 집합을 통해 노출됩니다.  이 클래스 집합을 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에 대한 *관리되는 클래스 인터페이스*라고 합니다.  다음 네임스페이스는 관리되는 클래스 인터페이스를 구성합니다.  
  
-   <xref:System.Drawing>  
  
-   <xref:System.Drawing.Drawing2D>  
  
-   <xref:System.Drawing.Imaging>  
  
-   <xref:System.Drawing.Text>  
  
-   <xref:System.Drawing.Printing>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]와 같은 그래픽 장치 인터페이스를 사용하면 특정 디스플레이 장치의 세부 정보를 염려하지 않고 화면 또는 프린터에 정보를 표시할 수 있습니다.  프로그래머가 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 클래스에서 제공하는 메서드를 호출합니다. 이러한 메서드가 다시 특정 장치 드라이버에 대한 적절한 호출을 수행합니다.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]는 그래픽 하드웨어에서 응용 프로그램을 분리합니다. 프로그래머가 장치 독립적인 응용 프로그램을 만들 수 있게 하는 것은 이러한 분리입니다.  
  
## 참고 항목  
 [그래픽 개요](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)