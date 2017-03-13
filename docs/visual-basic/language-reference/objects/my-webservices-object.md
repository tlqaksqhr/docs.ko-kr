---
title: "My.WebServices Object | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "My.WebServices"
  - "My.MyProject.WebServices"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.WebServices object"
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# My.WebServices Object
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

현재 프로젝트에서 참조하는 각 XML Web services의 단일 인스턴스를 만들고 액세스하기 위한 속성을 제공합니다.  
  
## 설명  
 `My.WebServices` 개체에서는 현재 프로젝트에서 참조하는 각 웹 서비스의 인스턴스를 제공합니다.  각 인스턴스는 필요 시 인스턴스화됩니다.  `My.WebServices` 개체의 속성을 통해 이 웹 서비스에 액세스할 수 있습니다.  속성의 이름은 속성이 액세스하는 웹 서비스 이름과 같습니다.  <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>에서 상속한 모든 클래스는 웹 서비스입니다.  프로젝트에 웹 서비스를 추가하는 방법은 [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)를 참조하십시오.  
  
 `My.WebServices` 개체는 현재 프로젝트에 연결된 웹 서비스만 노출하며  참조된 DLL에 선언된 웹 서비스에 대한 액세스는 제공하지 않습니다.  DLL이 제공하는 웹 서비스에 액세스하려면 *DllName*.*WebServiceName* 형식의 정규화된 웹 서비스 이름을 사용해야 합니다.  자세한 내용은 [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)를 참조하십시오.  
  
 해당 개체 및 속성은 웹 응용 프로그램에서 사용할 수 없습니다.  
  
## 속성  
 `My.WebServices` 개체의 각 속성은 현재 프로젝트에서 참조하는 웹 서비스의 인스턴스에 대한 액세스를 제공합니다.  속성의 이름은 속성이 액세스하는 웹 서비스의 이름과 같고 속성 형식은 웹 서비스의 형식과 같습니다.  
  
> [!NOTE]
>  이름이 충돌하는 경우 웹 서비스에 액세스하기 위한 속성 이름은 *RootNamespace*\_*Namespace*\_*ServiceName*입니다.  예를 들어 `Service1`이라는 두 웹 서비스를 가정해 봅니다.  이러한 서비스 중 하나가 루트 네임스페이스인 `WindowsApplication1`과 `Namespace1` 네임스페이스에 있는 경우 `My.WebServices.WindowsApplication1_Namespace1_Service1`을 사용하여 이 서비스에 액세스할 수 있습니다.  
  
 `My.WebServices` 개체의 속성 중 하나에 처음으로 액세스하면 웹 서비스의 새 인스턴스가 생성되고 저장됩니다.  다음에 해당 속성에 액세스하면 웹 서비스의 해당 인스턴스가 반환됩니다.  
  
 해당 웹 서비스의 속성에 `Nothing`을 할당하여 웹 서비스를 삭제할 수 있습니다.  속성 setter는 저장된 값에 `Nothing`을 할당합니다.  속성에 `Nothing` 이외의 값을 할당하는 경우 setter는 <xref:System.ArgumentException> 예외를 throw합니다.  
  
 `Is` 또는 `IsNot` 연산자를 사용하여 `My.WebServices` 개체의 속성이 웹 서비스의 인스턴스를 저장하는지 여부를 테스트할 수 있습니다.  이러한 연산자를 사용하여 속성 값이 `Nothing`인지 확인할 수 있습니다.  
  
> [!NOTE]
>  일반적으로 `Is` 또는 `IsNot` 연산자가 비교를 수행하려면 속성 값을 읽어야 합니다.  그러나 속성이 현재 `Nothing`을 저장하는 경우 속성은 웹 서비스의 새 인스턴스를 만든 다음 해당 인스턴스를 반환합니다.  Visual Basic 컴파일러는 `My.WebServices` 개체의 속성을 특별히 처리하므로 `Is` 또는 `IsNot` 연산자를 사용하여 값을 변경하지 않고 속성의 상태를 확인할 수 있습니다.  
  
## 예제  
 이 예제에서는 `TemperatureConverter` XML Web services의 `FahrenheitToCelsius` 메서드를 호출하고 결과를 반환합니다.  
  
 [!code-vb[VbVbalrMyWebService#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-webservices-object_1.vb)]  
  
 이 예제를 실행하려면 프로젝트가 `Converter`라는 웹 서비스를 참조해야 하고 해당 웹 서비스가 `ConvertTemperature` 메서드를 노출해야 합니다.  자세한 내용은 [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)를 참조하십시오.  
  
 이 코드는 웹 응용 프로그램 프로젝트에서 실행되지 않습니다.  
  
## 요구 사항  
  
### 프로젝트 형식별 사용 가능 여부  
  
|||  
|-|-|  
|프로젝트 형식|사용 가능|  
|Windows 응용 프로그램|**예**|  
|클래스 라이브러리|**예**|  
|콘솔 응용 프로그램|**예**|  
|Windows 컨트롤 라이브러리|**예**|  
|웹 컨트롤 라이브러리|**예**|  
|Windows 서비스|**예**|  
|웹 사이트|아니요|  
  
## 참고 항목  
 <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>   
 <xref:System.ArgumentException>   
 [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)