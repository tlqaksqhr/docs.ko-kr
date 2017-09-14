---
title: "COM Interop를 사용하여 데이터 마샬링"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
ms.assetid: 0bcdd7bf-5026-43eb-b08b-f03f90db9df9
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7e798f41f7c770fb0db0abf4a07e53cbaa6ccb40
ms.contentlocale: ko-kr
ms.lasthandoff: 08/21/2017

---
# <a name="marshaling-data-with-com-interop"></a>COM Interop를 사용하여 데이터 마샬링
COM interop는 관리 코드에서 COM 개체를 사용하고 관리되는 개체를 COM에 노출하는 기능을 모두 지원합니다. COM과의 데이터 마샬링 지원은 광범위하며 거의 항상 올바른 마샬링 동작을 제공합니다.  
  
 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]에는 다음과 같은 COM interop 도구가 포함됩니다.  
  
-   [형식 라이브러리 가져오기(Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) - COM 형식 라이브러리를 interop 어셈블리로 변환합니다. 이 어셈블리에서 interop 마샬링 서비스는 관리되는 메모리와 관리되지 않는 메모리 간에 데이터 마샬링을 수행하는 래퍼를 생성합니다.  
  
-   [형식 라이브러리 내보내기(Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) - 어셈블리에서 COM 형식 라이브러리를 생성하고 메서드 호출 중 마샬링을 수행하는 래퍼를 생성합니다.  
  
 이 섹션에서는 마샬러에 추가 형식 정보를 제공할 수 있는(제공해야 하는) 경우 interop 래퍼를 사용자 지정하는 프로세스를 설명합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [COM 데이터 형식](http://msdn.microsoft.com/en-us/f93ae35d-a416-4218-8700-c8218cc90061)  
 해당 관리되는 데이터 형식과 관리되지 않는 데이터 형식을 제공합니다.  
  
 [COM 호출 가능 래퍼 사용자 지정](http://msdn.microsoft.com/en-us/825177d3-4b2c-4723-82be-ce6ca2c34ace)  
 디자인 타임에 **MarshalAsAttribute** 특성을 사용하여 데이터 형식을 명시적으로 마샬링하는 방법을 설명합니다.  
  
 [런타임 호출 가능 래퍼 사용자 지정](http://msdn.microsoft.com/en-us/4652beaf-77d0-4f37-9687-ca193288c0be)  
 interop 어셈블리에서 형식의 마샬링 동작을 조정하는 방법 및 COM 형식을 수동으로 조정하는 방법을 설명합니다.  
  
 [방법: 관리 코드 DCOM을 WCF로 마이그레이션](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 보다 안전한 솔루션을 위해 관리되는 DCOM 코드를 WCF로 마이그레이션하는 방법을 설명합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [고급 COM 상호 운용성](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 COM 구성 요소를 .NET Framework 응용 프로그램으로 통합하는 방법에 대한 추가정보 링크를 제공합니다.  
  
 [어셈블리와 형식 라이브러리 간 변환 요약](http://msdn.microsoft.com/en-us/3a37eefb-a76c-4000-9080-7dbbf66a4896)  
 어셈블리에서 형식 라이브러리로 내보내기 변환 프로세스를 설명합니다.  
  
 [형식 라이브러리를 어셈블리로 변환 요약](http://msdn.microsoft.com/en-us/bf3f90c5-4770-4ab8-895c-3ba1055cc958)  
 형식 라이브러리에서 어셈블리 가져오기 변환 프로세스를 설명합니다.  
  
 [제네릭 형식을 통한 상호 운용](http://msdn.microsoft.com/en-us/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 COM 상호 운용성을 위해 제네릭 형식을 사용할 때 지원되는 작업을 설명합니다.

