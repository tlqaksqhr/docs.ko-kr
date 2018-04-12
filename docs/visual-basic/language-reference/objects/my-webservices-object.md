---
title: My.WebServices 개체
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a9f2c4017a1df8059f2cc57e7c30a96c474cfda0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="mywebservices-object"></a>My.WebServices 개체
만들고 현재 프로젝트에서 참조 하는 각 XML 웹 서비스의 단일 인스턴스에 액세스 하기 위한 속성을 제공 합니다.  
  
## <a name="remarks"></a>설명  
 `My.WebServices` 개체는 현재 프로젝트에서 참조하는 각 웹 서비스의 인스턴스를 제공합니다. 필요에 따라 각 인스턴스가 인스턴스화됩니다. `My.WebServices` 개체의 속성을 통해 이러한 웹 서비스에 액세스할 수 있습니다. 속성 이름은 속성이 액세스하는 웹 서비스의 이름과 같습니다. <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>에서 상속되는 모든 클래스는 웹 서비스입니다. 웹 서비스 프로젝트에 추가 하는 방법에 대 한 정보를 참조 하십시오. [응용 프로그램 웹 서비스에 액세스](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)합니다.  
  
 `My.WebServices` 개체만: 현재 프로젝트와 연결 된 웹 서비스를 제공 합니다. 참조 된 Dll에 선언 된 웹 서비스에 대 한 액세스를 제공 하지 않습니다. 폼에 웹 서비스의 정규화 된 이름을 사용 해야 하는 DLL을 제공 하는 웹 서비스에 액세스 하려면 *DllName*. *WebServiceName*합니다. 자세한 내용은 참조 [응용 프로그램 웹 서비스에 액세스](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)합니다.  
  
 개체와 해당 속성 웹 응용 프로그램에 사용할 수 없는 경우  
  
## <a name="properties"></a>속성  
 각 속성은 `My.WebServices` 개체는 현재 프로젝트에서 참조 하는 웹 서비스의 인스턴스에 대 한 액세스를 제공 합니다. 속성의 이름 속성에 액세스 하는 웹 서비스의 이름과 동일 이며 속성 유형 웹 서비스의 형식과 동일 합니다.  
  
> [!NOTE]
>  이름 충돌이 발생 하는 경우 웹 서비스에 액세스 하기 위한 속성 이름이 *RootNamespace*_*Namespace*\_*ServiceName*합니다. 예를 들어 이라는 두 개의 웹 서비스 `Service1`합니다. 루트 네임 스페이스에는 이러한 서비스 중 하나의 경우 `WindowsApplication1` 및 네임 스페이스에 `Namespace1`를 사용 하 여 서비스에 액세스할 수 `My.WebServices.WindowsApplication1_Namespace1_Service1`합니다.  
  
 처음으로 액세스 하면 중 하나는 `My.WebServices` 개체의 속성을 해당 웹 서비스의 새 인스턴스를 만들고 저장 합니다. 해당 속성의 후속 액세스는 웹 서비스의 해당 인스턴스를 반환 합니다.  
  
 할당 하 여 웹 서비스의 삭제할 수 있습니다 `Nothing` 해당 웹 서비스에 대 한 속성에 있습니다. 속성 setter 할당 `Nothing` 은 저장 된 값입니다. 이외의 모든 값을 할당 하는 경우 `Nothing` 속성 setter를 throw 한 <xref:System.ArgumentException> 예외입니다.  
  
 속성이 있는지 여부를 테스트할 수 있습니다는 `My.WebServices` 를 사용 하 여 웹 서비스의 인스턴스를 저장 하는 개체는 `Is` 또는 `IsNot` 연산자입니다. 이러한 연산자를 사용 하 여 속성의 값이 인지 확인 하기 `Nothing`합니다.  
  
> [!NOTE]
>  일반적으로 `Is` 또는 `IsNot` 연산자에는 비교를 수행 하는 속성의 값을 읽을 수 있습니다. 그러나 현재 저장 하는 경우 `Nothing`, 속성 웹 서비스의 새 인스턴스를 만들고 다음 해당 인스턴스를 반환 합니다. Visual Basic 컴파일러의 속성을 처리 하는 반면는 `My.WebServices` 알리고 특별, 개체는 `Is` 또는 `IsNot` 연산자를 해당 값을 변경 하지 않고 속성의 상태를 확인 합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 호출는 `FahrenheitToCelsius` 의 메서드는 `TemperatureConverter` XML 웹 서비스는 결과 반환 합니다.  
  
 [!code-vb[VbVbalrMyWebService#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-webservices-object_1.vb)]  
  
 이 예제가 작동 하려면 프로젝트 라는 웹 서비스를 참조 해야 `Converter`, 해당 웹 서비스를 노출 해야 하 고는 `ConvertTemperature` 메서드. 자세한 내용은 참조 [응용 프로그램 웹 서비스에 액세스](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)합니다.  
  
 이 코드는 웹 응용 프로그램 프로젝트에서 작동 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="availability-by-project-type"></a>프로젝트 형식에 따라 가용성  
  
|프로젝트 형식|사용 가능|  
|---|---|  
|Windows 응용 프로그램|**예**|  
|클래스 라이브러리|**예**|  
|콘솔 응용 프로그램|**예**|  
|Windows 컨트롤 라이브러리|**예**|  
|웹 컨트롤 라이브러리|**예**|  
|Windows 서비스|**예**|  
|웹 사이트|아니요|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>  
 <xref:System.ArgumentException>  
 [응용 프로그램 웹 서비스 액세스](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)
