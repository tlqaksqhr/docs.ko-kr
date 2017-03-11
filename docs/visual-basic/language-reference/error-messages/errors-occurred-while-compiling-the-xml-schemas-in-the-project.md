---
title: "Errors occurred while compiling the XML schemas in the project | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc36810"
  - "vbc36810"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36810"
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Errors occurred while compiling the XML schemas in the project
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

프로젝트에서 XML 스키마를 컴파일하는 동안 오류가 발생했습니다.이로 인해 XML IntelliSense를 사용할 수 없습니다.  
  
 프로젝트에 포함된 XSD\(XML 스키마 정의\) 스키마에 오류가 있습니다.  이 오류는 프로젝트의 기존 XSD 스키마 집합과 충돌하는 XSD 스키마\(.xsd\) 파일을 추가하는 경우 발생합니다.  
  
 **오류 ID:** BC36810  
  
### 이 오류를 해결하려면  
  
-   **오류 목록** 창에서 경고를 두 번 클릭합니다.  그러면 XSD 파일에서 경고의 원인이 되는 위치로 자동으로 이동됩니다.  XSD 스키마에서 오류를 수정합니다.  
  
-   필요한 모든 XSD 스키마 파일\(.xsd\)이 프로젝트에 있는지 확인합니다.  **솔루션 탐색기**에서 .xsd 파일을 보려면 **프로젝트** 메뉴에서 **모든 파일 표시**를 클릭해야 할 수 있습니다.  .xsd 파일을 마우스 오른쪽 단추로 클릭한 다음 **프로젝트에 포함**을 클릭하여 파일을 프로젝트에 포함합니다.  
  
-   XML to Schema 마법사를 사용하는 경우 같은 소스에서 스키마를 두 번 이상 유추하려고 하면 이 오류가 발생할 수 있습니다.  이 경우 프로젝트에서 기존 XSD 스키마 파일을 제거하고 새 XML to Schema 항목 템플릿을 추가한 다음 XML to Schema 마법사에서 프로젝트에 적용할 수 있는 XML 소스를 모두 제공합니다.  
  
-   XSD 스키마에서 오류를 확인할 수 없는 경우, XML 컴파일러에서는 정보가 충분하지 않아 자세한 오류 메시지를 제공하지 못합니다.  프로젝트에 포함된 .xsd 파일의 XML 네임스페이스가 Visual Studio의 XML 스키마 집합에 대해 식별된 XML 네임스페이스와 일치할 경우에는 자세한 오류 정보를 볼 수 있습니다.  
  
## 참고 항목  
 [오류 목록 창](/visual-studio/ide/reference/error-list-window)   
 [XML IntelliSense in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)