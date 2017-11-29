---
title: "COM Interop 소개(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interop assemblies
- COM interop [Visual Basic], about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 81a9d0fc7036ff1b821c46687541311f26113212
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="introduction-to-com-interop-visual-basic"></a>COM Interop 소개(Visual Basic)
구성 요소 개체 모델 (COM)에 다른 구성 요소를 응용 프로그램을 호스트 하는 기능을 노출 하는 개체 수 있습니다. COM 개체, 기본 windows 수 년에 대 한 프로그래밍 된 하는 동안 공용 언어 런타임 (CLR)에 대 한 설계 된 응용 프로그램에는 다양 한 이점을 제공 합니다.  
  
 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]응용 프로그램 대체 com 개발 된 그때 까지는 할 수 있습니다를 사용 하거나 사용 하 여 COM 개체를 만들 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]합니다. Com 상호 운용성 또는 *COM interop*를 전환 하는 동안 기존 COM 개체를 사용할 수 있습니다는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 자신의 진도에 있습니다.  
  
 사용 하 여는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] COM 구성 요소를 만들려면 등록이 필요 없는 COM interop를 사용할 수 있습니다. 이 기능을 사용 하면 여러 개의 버전이 컴퓨터에 설치 되 고 최종 사용자는 XCOPY 또는 FTP를 사용 응용 프로그램을 컴퓨터에 있는 적절 한 디렉터리로 복사할 실행 될 수 있습니다 하는 경우에 DLL 버전을 사용할 수를 제어할 수 있습니다. 자세한 내용은 참조 [등록이 필요 없는 COM Interop](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)합니다.  
  
## <a name="managed-code-and-data"></a>관리 코드 및 데이터  
 에 대 한 개발 된 코드는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 라고 *관리 코드*, CLR에서 사용 되는 메타 데이터를 포함 합니다. 사용 되는 데이터 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 응용 프로그램 이라고 *관리 되는 데이터* 런타임에 할당 및 메모리를 회수 하 고 수행 형식 검사와 같은 데이터 관련 작업을 관리 하기 때문입니다. 기본적으로 Visual Basic.NET에서는 관리 코드와 데이터를 되지만 관리 되지 않는 코드 및 interop 어셈블리 (이 페이지에 나중에 설명)를 사용 하 여 COM 개체의 데이터에 액세스할 수 있습니다.  
  
## <a name="assemblies"></a>어셈블리  
 어셈블리는 기본 빌딩 블록으로 한 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 응용 프로그램입니다. 빌드, 버전 지정 및 하나 이상의 파일을 포함 하는 단일 구현 단위로 배포 되는 기능 컬렉션입니다. 각 어셈블리에 어셈블리 매니페스트가 포함 됩니다.  
  
## <a name="type-libraries-and-assembly-manifests"></a>형식 라이브러리와 어셈블리 매니페스트  
 형식 라이브러리, 멤버 이름 및 데이터 형식과 같은 COM 개체의 특성에 설명 합니다. 에 대 한 동일한 기능을 수행 하는 어셈블리 매니페스트 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 응용 프로그램입니다. 다음에 대 한 정보를 포함 합니다.  
  
-   어셈블리 id, 버전, 문화권 및 디지털 서명을 합니다.  
  
-   어셈블리 구현을 구성 하는 파일입니다.  
  
-   어셈블리를 구성 하는 리소스 및 형식입니다. 내보내는 것 포함 됩니다.  
  
-   다른 어셈블리에 대 한 컴파일 시간 종속성입니다.  
  
-   올바르게 실행 하는 어셈블리에 필요한 사용 권한입니다.  
  
 어셈블리 및 어셈블리 매니페스트에 대 한 자세한 내용은 참조 하십시오. [어셈블리 및 전역 어셈블리 캐시](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)합니다.  
  
### <a name="importing-and-exporting-type-libraries"></a>가져오기 및 내보내기 형식 라이브러리  
 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]에 형식 라이브러리에서 정보를 가져올 수 있는 Tlbimp 유틸리티를 포함 한 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 응용 프로그램입니다. Tlbexp 유틸리티를 사용 하 여 어셈블리에서 형식 라이브러리를 생성할 수 있습니다.  
  
 Tlbimp와 Tlbexp에 대 한 정보를 참조 하십시오. [Tlbimp.exe (형식 라이브러리 가져오기)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382) 및 [Tlbexp.exe (형식 라이브러리 내보내기)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)합니다.  
  
## <a name="interop-assemblies"></a>Interop 어셈블리  
 Interop 어셈블리는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 간의 브리지 관리 및 관리 되지 않는 리소스는 어셈블리 코드를 하는 COM 개체 멤버 매핑 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 멤버를 관리 합니다. Interop 어셈블리를 Visual Basic.NET에서 만든 다양 한 상호 운용성 마샬링 같은 COM 개체, 작업의 세부 정보를 처리 합니다.  
  
## <a name="interoperability-marshaling"></a>상호 운용성 마샬링  
 모든 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 응용 프로그램에 사용 되는 프로그래밍 언어와 상관 없이 개체의 상호 운용성을 사용 하도록 설정 하는 공통 형식 집합을 공유 합니다. 매개 변수 및 COM 개체의 반환 값의 경우 관리 코드에서 사용 되는 데이터 형식을 사용 하는 경우가 종종 합니다. *상호 운용성 마샬링* 와 COM 개체를 이동 하는 동안에 매개 변수 및 반환 값을 해당 하는 데이터 형식으로는 프로세스입니다. 자세한 내용은 참조 [Interop 마샬링](../../../framework/interop/interop-marshaling.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)  
 [연습: COM 개체를 사용한 상속 구현](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [비관리 코드와의 상호 운용](https://msdn.microsoft.com/library/sd10k43k)  
 [상호 운용성 문제 해결](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [어셈블리 및 전역 어셈블리 캐시](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Tlbimp.exe(형식 라이브러리 가져오기)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)  
 [Tlbexp.exe(형식 라이브러리 내보내기)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [interop 마샬링](../../../framework/interop/interop-marshaling.md)  
 [등록이 필요 없는 COM interop](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)
