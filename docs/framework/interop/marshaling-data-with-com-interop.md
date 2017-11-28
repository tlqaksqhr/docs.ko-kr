---
title: "COM Interop를 사용하여 데이터 마샬링"
ms.custom: 
ms.date: 09/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2def27790a1727bda524b8c14a93f7b78127a569
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="marshaling-data-with-com-interop"></a>COM Interop를 사용하여 데이터 마샬링
COM interop는 관리 코드에서 COM 개체를 사용하고 관리되는 개체를 COM에 노출하는 기능을 모두 지원합니다. COM과의 데이터 마샬링 지원은 광범위하며 거의 항상 올바른 마샬링 동작을 제공합니다.  
  
 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]에는 다음과 같은 COM interop 도구가 포함됩니다.  
  
-   [형식 라이브러리 가져오기(Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) - COM 형식 라이브러리를 interop 어셈블리로 변환합니다. 이 어셈블리에서 interop 마샬링 서비스는 관리되는 메모리와 관리되지 않는 메모리 간에 데이터 마샬링을 수행하는 래퍼를 생성합니다.  
  
-   [형식 라이브러리 내보내기(Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) - 어셈블리에서 COM 형식 라이브러리를 생성하고 메서드 호출 중 마샬링을 수행하는 래퍼를 생성합니다.  
  
 다음 섹션에서는 마샬러에 추가 형식 정보를 수 있습니다 (또는 해야) 제공 하는 경우 interop 래퍼를 사용자 지정 하기 위한 프로세스를 설명 하는 항목을 연결 합니다.  
  
## <a name="in-this-section"></a>단원 내용  
[방법: 수동으로 래퍼 만들기](how-to-create-wrappers-manually.md)   
관리 되는 소스 코드에서 수동으로 COM 래퍼를 만드는 방법을 설명 합니다. 
 
 [방법: 관리 코드 DCOM을 WCF로 마이그레이션](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 가장 안전한 솔루션에 대 한 관리 되는 DCOM 코드를 WCF로 마이그레이션하는 방법에 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [COM 데이터 형식](https://msdn.microsoft.com/en-us/library/sak564ww(v=vs.100).aspx)  
 해당 관리되는 데이터 형식과 관리되지 않는 데이터 형식을 제공합니다.  
  
 [COM 호출 가능 래퍼 사용자 지정](https://msdn.microsoft.com/en-us/library/3bwc828w(v=vs.100).aspx)  
 사용 하 여 데이터 형식을 명시적으로 마샬링하는 방법에 설명 된 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 디자인 타임에 특성입니다.  
  
 [런타임 호출 가능 래퍼 사용자 지정](https://msdn.microsoft.com/en-us/library/e753eftz(v=vs.100).aspx)  
 interop 어셈블리에서 형식의 마샬링 동작을 조정하는 방법 및 COM 형식을 수동으로 조정하는 방법을 설명합니다.  
  
 [고급 COM 상호 운용성](https://msdn.microsoft.com/en-us/library/bd9cdfyx(v=vs.100).aspx)  
 COM 구성 요소를 .NET Framework 응용 프로그램으로 통합하는 방법에 대한 추가정보 링크를 제공합니다.  
  
 [어셈블리와 형식 라이브러리 간 변환 요약](https://msdn.microsoft.com/en-us/library/xk1120c3(v=vs.100).aspx)  
 어셈블리에서 형식 라이브러리로 내보내기 변환 프로세스를 설명합니다.  
  
 [형식 라이브러리를 어셈블리로 변환 요약](https://msdn.microsoft.com/en-us/library/k83zzh38(v=vs.100).aspx)  
 형식 라이브러리에서 어셈블리 가져오기 변환 프로세스를 설명합니다.  
  
 [제네릭 형식을 통한 상호 운용](https://msdn.microsoft.com/en-us/library/ms229590(v=vs.100).aspx)  
 COM 상호 운용성을 위해 제네릭 형식을 사용할 때 지원되는 작업을 설명합니다.
