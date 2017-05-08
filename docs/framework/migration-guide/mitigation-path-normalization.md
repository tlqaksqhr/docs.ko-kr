---
title: "완화: 경로 정규화 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0579bb975a62e512062b10d39c2967cdcd23438f
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-path-normalization"></a>완화: 경로 정규화
[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]을 대상으로 하는 앱부터, .NET Framework의 경로 정규화가 변경되었습니다.  
  
## <a name="what-is-path-normalization"></a>경로 정규화란?  
 경로 정규화 중에는 대상 운영 체제의 올바른 경로에 맞게 경로 또는 파일을 식별하는 문자열이 수정됩니다. 정규화에는 일반적으로 다음이 수행됩니다.  
  
-   구성 요소 및 디렉터리 구분 기호 정규화  
  
-   상대 경로에 현재 디렉터리 적용  
  
-   경로의 상대 디렉터리(`.`) 또는 부모 디렉터리(`..`) 평가  
  
-   지정된 문자 자르기  
  
## <a name="the-changes"></a>변경 내용  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱부터, 경로 정규화가 다음과 같이 변경되었습니다.  
  
-   런타임은 운영 체제의 [GetFullPathName](https://msdn.microsoft.com/library/windows/desktop/aa364963\(v=vs.85\).aspx) 함수를 지연시켜 경로를 정규화합니다.  
  
-   정규화 중에 더 이상 디렉터리 세그먼트의 끝(예: 디렉터리 이름 끝의 공백)이 잘리지 않습니다.  
  
-   완전 신뢰의 장치 경로 구문(`\\.\` 포함) 지원 및 mscorlib.dll `\\?\`에서 파일 I/O API 지원  
  
-   런타임에서 장치 구문 경로가 유효한지 확인하지 않습니다.  
  
-   대체 데이터 스트림에 액세스하기 위해 장치 구문을 사용할 수 있습니다.  
  
## <a name="impact"></a>영향  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 이상 버전을 대상으로 하는 앱의 경우 이러한 변경이 기본적으로 설정되어 있습니다. 이를 통해 메서드에서 이전에 액세스할 수 없는 경로에 액세스할 수 있게 되었으며 성능이 향상되었습니다.  
  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 및 이전 버전을 대상으로 하지만 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 이상에서 실행되는 앱은 이러한 변경에 의해 영향을 받지 않습니다.  
  
## <a name="mitigation"></a>완화  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 이상을 대상으로 하는 앱은 애플리케이션 구성 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음을 추가하여 이 동작을 옵트아웃(Opt out)하고 레거시 정규화를 사용할 수 있습니다.  
  
```xml  
  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
</runtime>  
  
```  
  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 또는 이전 버전을 대상으로 하지만 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 이상이 실행되는 앱은 응용 프로그램 .configuration 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음을 추가하여 경로 정규화에 대한 변경을 적용할 수 있습니다.  
  
```xml  
  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />    
</runtime>  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
