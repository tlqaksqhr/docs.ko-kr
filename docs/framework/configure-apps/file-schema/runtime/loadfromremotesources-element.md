---
title: "&lt;loadFromRemoteSources&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
caps.latest.revision: "31"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: efb968d40e54c7552fba0a592e759f9e83c92309
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltloadfromremotesourcesgt-element"></a>&lt;loadFromRemoteSources&gt; 요소
부여할지 여부를 원격 원본에서 어셈블리가 완전 신뢰를 지정 합니다.  
  
> [!NOTE]
>  Visual Studio 프로젝트의 오류 목록 또는 빌드 오류가 오류 메시지로 인해이 항목에 연결 하 고 된 경우 참조 [하는 방법: Visual Studio에서 웹의 어셈블리를 사용 하 여](http://msdn.microsoft.com/en-us/d8635b63-89a0-41aa-90f4-f351b2111070)합니다.  
  
 \<configuration>  
\<런타임 >  
\<loadFromRemoteSources >  
  
## <a name="syntax"></a>구문  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 부여할지 여부를 원격 원본에서 로드 된 어셈블리가 완전 신뢰를 지정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|원격 원본에서 응용 프로그램에 완전 신뢰를 부여 하지 마십시오. 이 값이 기본값입니다.|  
|`true`|원격 원본에서 응용 프로그램에 완전 신뢰를 부여 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework 버전 3.5 및 이전 버전에서 원격 위치에서 어셈블리를 로드 하는 경우 어셈블리가 실행 로드 된 영역에 의존 하는 권한 부여 집합으로 부분적으로 신뢰 됩니다. 예를 들어, 웹 사이트에서 어셈블리를 로드한 경우 인터넷 영역으로 로드되고 Internet 권한 집합을 부여 받습니다. 즉, 인터넷 샌드박스에서 실행 합니다. 해당 어셈블리를 실행 하려고 하는 경우는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 및 이상 버전에서 예외가 발생; 어셈블리에 대 한 샌드박스를 명시적으로 만들 하거나 해야 합니다 (참조 [하는 방법: 부분적으로 신뢰할 수 있는 코드 실행 샌드박스에서](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)), 또는 완전 신뢰에서 실행 합니다.  
  
 `<loadFromRemoteSources>` 요소를 사용하면 이전 버전의 .NET Framework에서 부분 신뢰로 실행되었던 어셈블리가 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 이상 버전에서 완전 신뢰로 실행되도록 지정할 수 있습니다. 기본적으로, 원격 어셈블리는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 이상에서 실행되지 않습니다. 원격 어셈블리를 실행하려면, 완전 신뢰로 실행하거나 원격 어셈블리를 실행할 샌드박스가 적용된 <xref:System.AppDomain>을 만들어야 합니다.  
  
> [!NOTE]
>  [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)]에서 로컬 네트워크 공유에 있는 어셈블리는 기본적으로 완전 신뢰 상태로 실행되고, `<loadFromRemoteSources>` 요소를 활성화할 필요가 없습니다.  
  
> [!NOTE]
>  응용 프로그램을 웹에서 복사한 경우, Windows에서는 해당 프로그램이 로컬 컴퓨터에 있더라도 웹 응용 프로그램이라는 플래그가 지정됩니다. 파일 속성을 변경 하 여 해당 지정을 변경 하거나 사용할 수 있습니다는 `<loadFromRemoteSources>` 완전 신뢰 어셈블리에 부여할 요소입니다. 또는 <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> 메서드를 사용하여 운영 체제가 웹에서 로드되었음을 표시하는 로컬 어셈블리를 로드할 수 있습니다.  
  
 `enabled` 특성이이 요소는 코드 액세스 보안 (CA)를 사용 하지 않도록 설정 하는 경우에 유효 합니다. 기본적으로 CAS 정책에 사용할 수 없습니다는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 이상 버전입니다. 설정한 경우 `enabled` 를 `true`, 원격 응용 프로그램에 완전 신뢰가 부여 됩니다.  
  
 경우 `<loadFromRemoteSources>``enabled` 로 설정 되지 않은 `true`, 다음과 같은 예외가 throw 됩니다.  
  
-   현재 도메인의 샌드 박싱 동작에서의 동작과에서 차이가 있는 [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)]합니다. CAS 정책을 사용 하지 않도록 설정할 고 샌드박스 아니어야 현재 도메인에 필요 합니다.  
  
-   로드 되는 어셈블리에서 가져오지 않았습니다 고 `MyComputer` 영역입니다.  
  
> [!NOTE]
>  발생할 수 있습니다는 <xref:System.IO.FileLoadException> 호스팅 컴퓨터에서 연결 된 폴더에서 파일을 로드 하려고 할 때 Windows Virtual PC 응용 프로그램에서 합니다. 통해 연결 된 폴더에서 파일을 로드 하려고 할 때에이 오류가 발생할 [원격 데스크톱 서비스](http://go.microsoft.com/fwlink/?LinkId=182775) (터미널 서비스). 예외를 방지 하려면 설정 `enabled` 를 `true`합니다.  
  
 설정의 `<loadFromRemoteSources>` 요소를 `true` 이 예외가 throw 되지 않도록 합니다. 있는지 있습니다 의존 하지 않고 sandbox에 공용 언어 런타임 보안을 위해 로드 된 어셈블리를 지정할 수 있도록 하 고 실행 되도록 지정할 수 완전 신뢰 합니다.  
  
> [!IMPORTANT]
>  완전 신뢰 어셈블리를 실행 해서는 안, 경우에이 구성 요소를 설정 하지 마십시오. 대신는 샌드박스를 만들 <xref:System.AppDomain> 를 로드할 어셈블리입니다.  
  
## <a name="configuration-file"></a>구성 파일  
 이 요소는 일반적으로 응용 프로그램 구성 파일에서 사용하지만 컨텍스트에 따라 다른 구성 파일에서도 사용할 수 있습니다. 자세한 내용은 문서 참조 [자세한 암시적 사용의 CAS 정책: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839) .NET 보안 블로그에서.  
  
## <a name="example"></a>예  
 다음 예에서는 원격 원본에서 응용 프로그램에 완전 신뢰를 부여 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [CAS 정책의 암시적 더 용도: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839)  
 [방법: 샌드박스에서 부분적으로 신뢰할 수 있는 코드 실행](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
