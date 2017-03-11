---
title: "Introduction to COM Interop (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "interop assemblies"
  - "COM interop, about COM interop"
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Introduction to COM Interop (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

COM\(Component Object Model\)을 사용하면 개체의 기능을 다른 구성 요소 및 호스트 응용 프로그램에 노출할 수 있습니다.  COM 개체는 오랫동안 Windows 프로그래밍의 기초였지만 CLR\(공용 언어 런타임\)에 맞게 응용 프로그램을 개발하면 많은 이점을 얻을 수 있습니다.  
  
 결국에는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 응용 프로그램이 COM으로 개발한 응용 프로그램을 대신할 것입니다.  그때까지는 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]에서 COM 개체를 사용하거나 만들어야 할 수 있습니다.  COM과의 상호 운용\(또는 *COM interop*\) 기능은 기존 COM 개체를 계속 사용하면서 상황에 맞게 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]로 전환할 수 있도록 해 줍니다.  
  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]를 사용하여 COM 구성 요소를 만들면 등록이 필요 없는 COM interop를 사용할 수 있습니다.  이렇게 하면 컴퓨터에 설치된 DLL 버전이 둘 이상일 때 활성화되는 DLL 버전을 제어할 수 있고 최종 사용자는 XCOPY 또는 FTP를 사용하여 응용 프로그램을 자신의 컴퓨터에서 실행할 수 있는 적절한 디렉터리로 복사할 수 있습니다.  자세한 내용은 [등록이 필요 없는 COM Interop](../Topic/Registration-Free%20COM%20Interop.md)를 참조하십시오.  
  
## 관리 코드 및 데이터  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]용으로 개발된 코드는 *관리 코드*라고 하며 CLR에 사용되는 메타데이터를 포함합니다.  [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 응용 프로그램에 사용되는 데이터는 *관리되는 데이터*라고 합니다. 이는 런타임에서 메모리 할당\/회수 및 형식 검사 수행 등의 데이터 관련 작업을 관리하기 때문입니다.  기본적으로 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)]에서는 관리 코드와 관리되는 데이터를 사용하지만 interop 어셈블리를 사용하여 COM 개체의 비관리 코드와 관리되지 않는 데이터에 액세스할 수도 있습니다\(뒤쪽 참조\).  
  
## 어셈블리  
 어셈블리는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 응용 프로그램을 구성하는 기본 빌딩 블록으로,  하나 이상의 파일을 포함하는 단일 구현 단위로 빌드, 버전 지정 및 배포되는 기능 모음입니다.  각 어셈블리에 어셈블리 매니페스트가 하나씩 있습니다.  
  
## 형식 라이브러리 및 어셈블리 매니페스트  
 형식 라이브러리는 멤버 이름이나 데이터 형식과 같은 COM 개체의 특성에 대해 설명합니다.  어셈블리 매니페스트는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 응용 프로그램에 대해 동일한 기능을 수행합니다.  여기에는 다음에 대한 정보가 포함됩니다.  
  
-   어셈블리 ID, 버전, 문화권 및 디지털 서명  
  
-   어셈블리 구현을 구성하는 파일  
  
-   어셈블리를 구성하는 형식과 리소스입니다.  여기에는 어셈블리에서 내보내는 형식과 리소스도 포함됩니다.  
  
-   다른 어셈블리에 대한 컴파일 타임 종속성  
  
-   어셈블리의 올바른 실행을 위해 필요한 권한  
  
 어셈블리 및 어셈블리 매니페스트에 대한 자세한 내용은 [어셈블리 및 전역 어셈블리 캐시](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)를 참조하십시오.  
  
### 형식 라이브러리 가져오기 및 내보내기  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]에 포함된 Tlbimp 유틸리티를 사용하여 형식 라이브러리의 정보를 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 응용 프로그램으로 가져올 수 있습니다.  Tlbexp 유틸리티를 사용하면 어셈블리에서 형식 라이브러리를 생성할 수 있습니다.  
  
 Tlbimp 및 Tlbexp에 대한 자세한 내용은 [Tlbimp.exe\(형식 라이브러리 가져오기\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md) 및 [Tlbexp.exe\(형식 라이브러리 내보내기\)](../Topic/Tlbexp.exe%20\(Type%20Library%20Exporter\).md)를 참조하십시오.  
  
## Interop 어셈블리  
 Interop 어셈블리는 관리 코드와 비관리 코드 사이에서 다리 역할을 하는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 어셈블리로, COM 개체 멤버를 해당하는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 관리 멤버에 매핑합니다.  [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)]를 사용하여 만든 Interop 어셈블리는 상호 운용성 마샬링과 같이 COM 개체에 관련된 많은 작업을 처리합니다.  
  
## 상호 운용성 마샬링  
 모든 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 응용 프로그램은 사용된 프로그래밍 언어에 관계없이 개체 간의 상호 운용성을 허용하는 공통 형식 집합을 공유합니다.  COM 개체의 매개 변수 및 반환 값에는 관리 코드에서 사용되는 것과 다른 데이터 형식이 사용되는 경우가 종종 있습니다.  *상호 운용성 마샬링*은 COM 개체와의 이동에 있어 해당하는 데이터 형식으로 매개 변수 및 반환 값을 패키지로 만드는 프로세스입니다.  자세한 내용은 [Interop 마샬링](../Topic/Interop%20Marshaling.md)를 참조하십시오.  
  
## 참고 항목  
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Walkthrough: Implementing Inheritance with COM Objects](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [비관리 코드와의 상호 운용](../Topic/Interoperating%20with%20Unmanaged%20Code.md)   
 [Troubleshooting Interoperability](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)   
 [어셈블리 및 전역 어셈블리 캐시](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Tlbimp.exe\(형식 라이브러리 가져오기\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)   
 [Tlbexp.exe\(형식 라이브러리 내보내기\)](../Topic/Tlbexp.exe%20\(Type%20Library%20Exporter\).md)   
 [Interop 마샬링](../Topic/Interop%20Marshaling.md)   
 [등록이 필요 없는 COM Interop](../Topic/Registration-Free%20COM%20Interop.md)