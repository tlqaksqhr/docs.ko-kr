---
title: '방법: Svcutil.exe를 사용하여 컴파일된 서비스 코드 유효성 검사'
ms.date: 03/30/2017
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
ms.openlocfilehash: 9e7bdf98f578e9b5f9ef2be9c46ccbe811358467
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490463"
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a>방법: Svcutil.exe를 사용하여 컴파일된 서비스 코드 유효성 검사
사용할 수는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 서비스를 호스팅하지 않고 서비스 구현 및 구성에 오류를 검색 하 합니다.  
  
### <a name="to-validate-a-service"></a>서비스의 유효성을 검사하려면  
  
1.  서비스를 실행 파일과 하나 이상의 종속 어셈블리로 컴파일합니다.  
  
2.  SDK 명령 프롬프트를 엽니다.  
  
3.  명령 프롬프트에서 다음 형식을 사용하여 Svcutil.exe 도구를 실행합니다. 서비스 Validationsection 다양 한 매개 변수에 대 한 자세한 내용은 참조는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 항목입니다.  
  
    ```  
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     유효성을 검사할 서비스의 구성 이름을 나타내려면 `/serviceName` 옵션을 사용해야 합니다.  
  
     `assemblyPath` 인수는 유효성을 검사할 서비스 형식이 포함된 하나 이상의 어셈블리와 서비스에 대한 실행 파일 경로를 지정합니다. 서비스 구성을 제공하려면 실행 가능한 어셈블리에 연결된 구성 파일이 있어야 합니다. 표준 명령줄 와일드카드를 사용하여 여러 어셈블리를 제공할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 명령은 myServiceHost.exe 실행 파일에 구현된 myServiceName 서비스를 사용합니다.  서비스(myServiceHost.exe.config)에 대한 구성 파일이 자동으로 로드됩니다.  
  
```  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a>참고 항목  
 [ServiceModel Metadata 유틸리티 도구(Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
