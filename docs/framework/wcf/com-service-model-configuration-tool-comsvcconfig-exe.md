---
title: "COM+ 서비스 모델 구성 도구(ComSvcConfig.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "WCF, COM+ 통합"
  - "Windows Communication Foundation, COM+ 통합"
ms.assetid: 7717c6c2-85fc-418b-a8ed-bad8e61cec5c
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# COM+ 서비스 모델 구성 도구(ComSvcConfig.exe)
COM\+ 서비스 모델 구성 명령줄 도구\(ComSvcConfig.exe\)를 사용하면 COM\+ 인터페이스를 웹 서비스로 노출하도록 구성할 수 있습니다.  
  
## 구문  
  
```  
  
ComSvcConfig.exe /install | /uninstall | /list [/application:<ApplicationID | ApplicationName>] [/contract:<ClassID | ProgID | *,InterfaceID | InterfaceName | *>] [/hosting:<complus | was>] [/webSite:<WebsiteName>] [/webDirectory:<WebDirectoryName>] [/mex] [/id] [/nologo] [/verbose] [/help] [/partial]  
```  
  
## 설명  
  
> [!NOTE]
>  ComSvcConfig.exe를 사용하려면 로컬 컴퓨터의 관리자여야 합니다.  
  
 이 도구는 다음 위치에 있습니다.  
  
 %SystemRoot%\\Microsoft.Net\\Framework\\v3.0\\Windows Communication Foundation\\  
  
 ComSvcConfig.exe에 대한 자세한 내용은 [방법: COM\+ 서비스 모델 구성 도구 사용](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)을 참조하십시오.  
  
 다음 표에서는 ComSvcConfig.exe에 사용할 수 있는 모드에 대해 설명합니다.  
  
|옵션|설명|  
|--------|--------|  
|`install`|서비스 모델 통합을 위해 COM\+ 인터페이스에 대한 구성을 설치합니다.<br /><br /> 약식은 `/i`입니다.|  
|`uninstall`|서비스 모델 통합에서 COM\+ 인터페이스에 대한 구성을 제거합니다.<br /><br /> 약식은 `/u`입니다.|  
|`list`|서비스 모델 통합을 위해 구성된 인터페이스가 있는 COM\+ 응용 프로그램 및 구성 요소에 대한 정보를 나열합니다.<br /><br /> 약식은 `/l`입니다.|  
  
 다음 표에서는 ComSvcConfig.exe에 사용할 수 있는 플래그에 대해 설명합니다.  
  
|옵션|설명|  
|--------|--------|  
|`/application:<` *ApplicationID*  `&#124;`  *ApplicationName* `>`|구성할 COM\+ 응용 프로그램을 지정합니다.<br /><br /> 약식은 `/a`입니다.|  
|`/contract:<` *ClassID*  `&#124;`  *ProgID*  `&#124; *,` *InterfaceID*  `&#124;`  *InterfaceName*  `&#124; *` `>`|서비스의 계약으로 구성할 COM\+ 구성 요소 및 인터페이스를 지정합니다.<br /><br /> 약식은 `/c`입니다.<br /><br /> 와일드카드 문자\(\*\)를 구성 요소 및 인터페이스 이름을 지정할 때 사용할 수 있지만 원하지 않은 인터페이스가 노출될 수 있으므로 이를 사용하지 않는 것이 좋습니다.|  
|`/hosting:<` *complus*  `&#124;`  *was* `>`|COM\+ 호스팅 모드 또는 웹 호스팅 모드를 사용할지 지정합니다.<br /><br /> 약식은 `/h`입니다.<br /><br /> COM\+ 호스팅 모드를 사용하려면 COM\+ 응용 프로그램을 명시적으로 활성화해야 합니다.웹 호스팅 모드를 사용하면 필요에 따라 COM\+ 응용 프로그램을 자동으로 활성화할 수 있습니다.COM\+ 응용 프로그램이 라이브러리 응용 프로그램인 경우 IIS\(인터넷 정보 서비스\) 프로세스에서 실행됩니다.COM\+ 응용 프로그램이 서버 응용 프로그램인 경우 Dllhost.exe 프로세스에서 실행됩니다.|  
|`/webSite:<` *WebsiteName* `>`|웹 호스팅 모드를 사용할 때 호스팅할 웹 사이트를 지정합니다. `/hosting` 플래그를 참조하십시오.<br /><br /> 약식은 `/w`입니다.<br /><br /> 웹 사이트가 지정되지 않은 경우에는 기본 웹 사이트가 사용됩니다.|  
|`/webDirectory:<` *WebDirectoryName* `>`|웹 호스팅을 사용할 때 호스팅할 가상 디렉터리를 지정합니다. `/hosting` 플래그를 참조하십시오.<br /><br /> 약식은 `/d`입니다.|  
|`/mex`|서비스에서 계약 정의를 검색하려는 클라이언트를 지원하기 위해 기본 서비스 구성에 MEX\(메타데이터 교환\) 서비스 끝점을 추가합니다.<br /><br /> 약식은 `/x`입니다.|  
|`/id`|응용 프로그램, 구성 요소 및 인터페이스 정보를 ID로 표시합니다.<br /><br /> 약식은 `/k`입니다.|  
|`/nologo`|ComSvcConfig.exe에서 로고가 표시되지 않도록 합니다.<br /><br /> 약식은 `/n`입니다.|  
|`/verbose`|발생한 모든 오류 이외에 경고 또는 정보 텍스트를 모두 출력합니다.<br /><br /> 약식은 `/v`입니다.|  
|`/help`|사용 메시지를 표시합니다.<br /><br /> 약식은 `/?`입니다.|  
|`/partial`|지정한 인터페이스에 노출할 수 있는 하나 이상의 메서드 서명이 있는 경우 서비스 구성을 생성합니다.서비스 초기화 시 호환되는 메서드는 서비스 계약에 작업으로 나타나며 호환되지 않는 메서드는 무시되고 서비스 계약에 표시되지 않습니다.<br /><br /> 이 플래그가 없으면 지정한 인터페이스에 하나 이상의 호환되지 않는 메서드가 있는 경우 도구에서 서비스 구성을 생성하지 않습니다.|  
  
## 예제  
  
### 설명  
 다음 예제는 OnlineStore COM\+ 응용 프로그램에 있는 `ItemOrders.IFinancial` 구성 요소의 `IFinances` 인터페이스를 웹 서비스로 노출되는 인터페이스 집합에 COM\+ 호스팅 모드를 사용하여 추가합니다.발생한 모든 오류 이외에 경고를 모두 출력합니다.  
  
### 코드  
  
```  
ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose  
```  
  
### 설명  
 다음 예제는 OnlineWarehouse COM\+ 응용 프로그램에 있는 `ItemInventory.Warehouse` 구성 요소의 `IStockLevels` 인터페이스를 웹 서비스로 노출되는 인터페이스 집합에 웹 호스팅 모드를 사용하여 추가합니다.웹 서비스는 IIS의 OnlineWarehouse 가상 디렉터리에서 웹 호스팅됩니다.  
  
### 코드  
  
```  
ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse  
```  
  
### 설명  
 다음 예제는 OnlineStore COM\+ 응용 프로그램에 있는 `ItemOrders.Financial` 구성 요소의 `IFinances` 인터페이스를 웹 서비스로 노출되는 인터페이스 집합에서 제거합니다.  
  
### 코드  
  
```  
ComSvcConfig.exe /uninstall /application:OnlineStore /interface:ItemOrders.Financial,IFinances /hosting:complus  
```  
  
### 설명  
 다음 예제는 현재 노출된 COM\+ 호스팅 인터페이스와 함께 로컬 컴퓨터의 OnlineStore COM\+ 응용 프로그램에 대한 해당 주소 및 바인딩 세부 내용을 나열합니다.  
  
### 코드  
  
```  
ComSvcConfig.exe /list /application:OnlineStore /hosting:complus  
```  
  
## 참고 항목  
 [방법: COM\+ 서비스 모델 구성 도구 사용](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)