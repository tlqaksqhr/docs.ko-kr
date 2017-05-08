---
title: "In-Process Side-by-Side 실행 | Microsoft Docs"
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
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "in-process side-by-side 실행"
  - "side-by-side 실행, in-process"
ms.assetid: 18019342-a810-4986-8ec2-b933a17c2267
caps.latest.revision: 25
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 25
---
# In-Process Side-by-Side 실행
[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터는 in\-process side\-by\-side 호스팅을 사용하여 단일 프로세스에서 여러 버전의 CLR\(공용 언어 런타임\)을 실행할 수 있습니다.  관리되는 COM 구성 요소는 프로세스에서 로드한 .NET Framework 버전과 상관없이 기본적으로 해당 구성 요소가 빌드된 .NET Framework 버전을 사용하여 실행됩니다.  
  
## Background  
 .NET Framework에서는 관리되는 코드 응용 프로그램을 위해 side\-by\-side 호스팅을 항상 제공해 왔지만 관리되는 COM 구성 요소에 대해서는 이러한 기능을 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]부터 제공했습니다.  그 이전에는 프로세스로 로드된 관리되는 COM 구성 요소가 이미 로드되어 있는 런타임 버전 또는 .NET Framework의 최신 설치 버전을 사용하여 실행되었습니다.  이 버전이 COM 구성 요소와 호환되지 않으면 해당 구성 요소가 실패하게 됩니다.  
  
 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]에서는 다음을 보장하기 위해 side\-by\-side 호스팅의 새 접근법을 제공합니다.  
  
-   .NET Framework의 새 버전을 설치해도 기존 응용 프로그램에 영향을 주지 않습니다.  
  
-   응용 프로그램은 빌드된 버전의 .NET Framework를 기반으로 실행됩니다.  명시적으로 지정된 경우가 아니라면 응용 프로그램은 .NET Framework의 새 버전을 사용하지 않습니다.  그러나 응용 프로그램은 .NET Framework의 새 버전을 사용하기 위해 쉽게 전환될 수 있습니다.  
  
## 사용자 및 개발자에 대한 영향  
  
-   **최종 사용자 및 시스템 관리자**.  이제 이러한 사용자는 런타임의 새 버전을 독립적으로 또는 응용 프로그램과 함께 설치할 경우 컴퓨터에 아무런 영향을 주지 않는다는 확신을 가질 수 있습니다.  기존 응용 프로그램은 이전과 동일하게 계속 실행됩니다.  
  
-   **응용 프로그램 개발자**.  Side\-by\-side 호스팅은 응용 프로그램 개발자에게 거의 영향을 미치지 않습니다.  기본적으로 응용 프로그램은 빌드된 .NET Framework의 버전을 기반으로 실행되며, 이는 이전과 동일하게 적용됩니다.  그러나 개발자는 이 동작을 재정의하고 응용 프로그램이 새로운 .NET Framework 버전에서 실행되도록 지정할 수 있습니다\([시나리오 2](#scenarios) 참조\).  
  
-   **라이브러리 개발자 및 소비자**.  Side\-by\-side 호스팅은 라이브러리 개발자가 직면하는 호환성 문제를 해결해 주지 않습니다.  직접 참조 또는 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 호출을 통해 응용 프로그램에서 직접 로드한 라이브러리는 해당 라이브러리가 로드된 <xref:System.AppDomain>의 런타임을 계속 사용합니다.  라이브러리는 지원할 .NET Framework의 모든 버전을 대상으로 테스트해야 합니다.  [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 런타임을 사용하여 컴파일된 응용 프로그램에 이전 런타임을 사용하여 빌드된 라이브러리가 포함되어 있으면 해당 라이브러리는 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 런타임도 사용하게 됩니다.  그러나 이전 런타임을 사용하여 빌드된 응용 프로그램과 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]을 사용하여 빌드된 라이브러리가 있으면 응용 프로그램에서 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 도 사용하도록 해야 합니다\([시나리오 3](#scenarios) 참조\).  
  
-   **관리되는 COM 구성 요소 개발자**.  이전까지 관리되는 COM 구성 요소는 컴퓨터에 설치된 런타임의 최신 버전을 사용하여 자동으로 실행되었습니다.  그러나 이제는 COM 구성 요소가 빌드된 런타임 버전을 기반으로 해당 구성 요소를 실행할 수 있습니다.  
  
     다음 표에서 알 수 있듯이 .NET Framework 버전 1.1을 사용하여 빌드된 구성 요소는 버전 4 구성 요소와 함께 실행될 수 있습니다. 그러나 버전의 2.0, 3.0 또는 3.5의 경우 side\-by\-side 호스팅을 사용할 수 없기 때문에 이러한 버전의 구성 요소와 .NET Framework 버전 1.1을 사용하여 빌드된 구성 요소가 함께 실행될 수는 없습니다.  
  
    |.NET Framework 버전|1.1|2.0 \- 3.5|4|  
    |-----------------------|---------|----------------|-------|  
    |1.1|해당 없음|아니요|예|  
    |2.0 \- 3.5|아니요|해당 없음|예|  
    |4|예|예|해당 없음|  
  
> [!NOTE]
>  .NET Framework 버전 3.0 및 3.5는 버전 2.0을 기반으로 증분 방식으로 빌드되어 있기 때문에 두 버전을 함께 실행할 필요가 없습니다.  두 버전은 본질적으로 동일합니다.  
  
<a name="scenarios"></a>   
## 일반적인 Side\-by\-Side 호스팅 시나리오  
  
-   **시나리오 1:** .NET Framework의 이전 버전을 사용하여 빌드된 COM 구성 요소를 사용하는 네이티브 응용 프로그램.  
  
     설치된 .NET Framework 버전: [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 및 COM 구성 요소에서 사용하는 .NET Framework의 모든 기타 버전.  
  
     수행할 작업: 이 시나리오에서는 없습니다.  COM 구성 요소는 해당 구성 요소가 등록된 .NET Framework의 버전을 사용하여 실행됩니다.  
  
-   **시나리오 2**: [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)]을 사용하여 빌드된 관리되는 응용 프로그램이며, [!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)]을 사용하여 실행하는 방법을 선호하지만 버전 2.0이 없으면 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]을 기반으로 실행하려는 응용 프로그램.  
  
     설치된 .NET Framework 버전: .NET Framework의 이전 버전 및 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].  
  
     수행할 작업: 응용 프로그램 디렉터리의 [응용 프로그램 구성 파일](../../../docs/framework/configure-apps/index.md) 에서 [\<startup\> element](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) 와 [\<supportedRuntime\> 요소](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 집합을 다음과 같이 사용합니다.  
  
    ```  
    <configuration>  
      <startup >  
        <supportedRuntime version="v2.0.50727" />  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
-   **시나리오 3:** .NET Framework의 이전 버전을 사용하여 빌드된 COM 구성 요소를 사용하는 네이티브 응용 프로그램이며, [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]을 사용하여 실행하려는 응용 프로그램.  
  
     설치된 .NET Framework 버전: [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].  
  
     수행할 작업: 응용 프로그램 디렉터리의 응용 프로그램 구성 파일에서 `useLegacyV2RuntimeActivationPolicy` 특성이 `true`로 설정된 `<startup>` 요소 및 `<supportedRuntime>` 요소 집합을 다음과 같이 사용합니다.  
  
    ```  
    <configuration>  
      <startup useLegacyV2RuntimeActivationPolicy="true">  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
## 예제  
 다음 예제는 관리되는 COM 구성 요소의 컴파일에 사용된 .NET Framework 버전을 사용하여 해당 구성 요소를 실행하는 관리되지 않는 COM 호스트를 보여 줍니다.  
  
 다음 예제를 실행하기 위해서, [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)]를 사용하여 다음 관리 COM 구성 요소를 컴파일하고 등록합니다.  구성 요소를 등록하기 위해서, **프로젝트** 메뉴에서, **속성**을 클릭하고, **빌드** 탭을 클릭한 다음 **COM interop를 위한 등록** 확인란을 선택합니다.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Runtime.InteropServices;  
  
namespace BasicComObject  
{  
    [ComVisible(true), Guid("9C99C4B5-CA54-4c58-8988-49B6811BA53B")]  
    public class MyObject : SimpleObjectModel.IPrintInfo  
    {  
        public MyObject()  
        {  
        }  
        public void PrintInfo()  
        {  
            Console.WriteLine("MyObject was activated in {0} runtime in:\n\tAppDomain {1}:{2}", System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion(), AppDomain.CurrentDomain.Id, AppDomain.CurrentDomain.FriendlyName);  
        }  
    }  
}  
```  
  
 관리되지 않는 다음 C\+\+ 응용 프로그램을 컴파일합니다. 이 응용 프로그램은 이전 예제에서 만든 COM 개체를 활성화합니다.  
  
```  
#include "stdafx.h"  
#include <string>  
#include <iostream>  
#include <objbase.h>  
#include <string.h>  
#include <process.h>  
  
using namespace std;  
  
int _tmain(int argc, _TCHAR* argv[])  
{  
    char input;  
    CoInitialize(NULL) ;  
    CLSID clsid;  
    HRESULT hr;  
    HRESULT clsidhr = CLSIDFromString(L"{9C99C4B5-CA54-4c58-8988-49B6811BA53B}",&clsid);  
    hr = -1;  
    if (FAILED(clsidhr))  
    {  
        printf("Failed to construct CLSID from String\n");  
    }  
    UUID id = __uuidof(IUnknown);  
    IUnknown * pUnk = NULL;  
    hr = ::CoCreateInstance(clsid,NULL,CLSCTX_INPROC_SERVER,id,(void **) &pUnk);  
    if (FAILED(hr))  
    {  
        printf("Failed CoCreateInstance\n");  
    }else  
    {  
        pUnk->AddRef();  
        printf("Succeeded\n");  
    }  
  
    DISPID dispid;  
    IDispatch* pPrintInfo;  
    pUnk->QueryInterface(IID_IDispatch, (void**)&pPrintInfo);  
    OLECHAR FAR* szMethod[1];  
    szMethod[0]=OLESTR("PrintInfo");   
    hr = pPrintInfo->GetIDsOfNames(IID_NULL,szMethod, 1, LOCALE_SYSTEM_DEFAULT, &dispid);  
    DISPPARAMS dispparams;  
    dispparams.cNamedArgs = 0;  
    dispparams.cArgs = 0;  
    VARIANTARG* pvarg = NULL;  
    EXCEPINFO * pexcepinfo = NULL;  
    WORD wFlags = DISPATCH_METHOD ;  
;  
    LPVARIANT pvRet = NULL;  
    UINT * pnArgErr = NULL;  
    hr = pPrintInfo->Invoke(dispid,IID_NULL, LOCALE_USER_DEFAULT, wFlags,  
        &dispparams, pvRet, pexcepinfo, pnArgErr);  
    printf("Press Enter to exit");  
    scanf_s("%c",&input);  
    CoUninitialize();  
    return 0;  
}  
  
```  
  
## 참고 항목  
 [\<startup\> 요소](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)   
 [\<supportedRuntime\> 요소](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)