---
title: "지역화 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "응용 프로그램 개발[.NET Framework], 지역화"
  - "코드 블록"
  - "culture, 지역화"
  - "전역 응용 프로그램, 지역화"
  - "전역화[.NET Framework], 지역화"
  - "국가별 응용 프로그램[.NET Framework], 지역화"
  - "지역화[.NET Framework], 지역화 정보"
  - "리소스 지역화"
  - "사용자 인터페이스 블록"
  - "지역화 대비 응용 프로그램, 지역화"
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# 지역화
지역화는 응용 프로그램 리소스를 응용 프로그램에서 지원할 각 culture에 맞는 지역화된 버전으로 번역하는 과정입니다.  [지역화 가능성 검토](../../../docs/standard/globalization-localization/localizability-review.md) 단계를 완료하여 전역화된 응용 프로그램이 지역화될 수 있는지 확인한 후에만 지역화를 진행하도록 합니다.  
  
 지역화될 수 있는 응용 프로그램은 두 개의 개념적 블록인 모든 사용자 인터페이스 요소를 포함하는 블록과 실행 코드를 포함하는 블록으로 분리됩니다.  사용자 인터페이스 블록에는 중립 culture에 대한 문자열, 오류 메시지, 대화 상자, 메뉴, 포함된 개체 리소스 등의 지역화 가능 사용자 인터페이스 요소만 들어 있습니다.  코드 블록에는 지원되는 모든 culture에서 사용할 응용 프로그램 코드만 들어 있습니다.  공용 언어 런타임에서는 응용 프로그램 실행 코드를 해당 리소스에서 분리하는 위성 어셈블리 리소스 모델을 지원합니다.  이 모델의 구현에 대한 자세한 내용은 [데스크톱 응용 프로그램의 리소스](../../../docs/framework/resources/index.md)를 참조하십시오.  
  
 응용 프로그램의 모든 지역화된 버전에 대해 대상 culture에 해당하는 언어로 번역되어 지역화된 사용자 인터페이스 블록이 들어 있는 새 위성 어셈블리를 추가합니다.  모든 culture의 코드 블록은 그대로 유지되어야 합니다.  사용자 인터페이스 블록의 지역화된 버전과 코드 블록을 조합하면 응용 프로그램의 지역화된 버전이 됩니다.  
  
 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]에서는 대상 문화권에 대해 Windows Forms을 신속하게 지역화할 수 있는 Windows Forms 리소스 편집기\(Winres.exe\)를 제공합니다.  이 도구 사용에 대한 자세한 내용은 [Winres.exe\(Windows Forms 리소스 편집기\)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)를 참조하십시오.  
  
## 참고 항목  
 [전역화 및 지역화](../../../docs/standard/globalization-localization/index.md)   
 [지역화 가능성 검토](../../../docs/standard/globalization-localization/localizability-review.md)   
 [전역화](../../../docs/standard/globalization-localization/globalization.md)   
 [데스크톱 응용 프로그램의 리소스](../../../docs/framework/resources/index.md)