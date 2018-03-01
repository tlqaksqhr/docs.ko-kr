---
title: "연습-형식 공급자 (F #)를 사용 하 여 웹 서비스에 액세스"
description: "WSDL 서비스에 액세스 하려면 F # 3.0에서 사용할 수 있는 WSDL 웹 서비스 설명 언어 () 형식 공급자를 사용 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 63374fa9-8fb8-43ac-bcb9-ef2290d9f851
ms.openlocfilehash: 2929198172a4e9f908daa64af19208e07859263f
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-accessing-a-web-service-by-using-type-providers"></a>연습: 형식 공급자를 사용하여 웹 서비스에 액세스

> [!NOTE]
이 가이드는 F # 3.0 용으로 작성 된 하 고 업데이트 됩니다.  최신 크로스 플랫폼 형식 공급자에 대해서는 [FSharp.Data](https://fsharp.github.io/FSharp.Data/)를 참조하세요.

> [!NOTE]
API 참조 링크 MSDN을 이동 합니다.  docs.microsoft.com API 참조가 완전하지 않습니다.

이 연습에서는 F # 3.0 WSDL 서비스에 액세스할 수 있는 WSDL 웹 서비스 설명 언어 () 형식 공급자를 사용 하는 방법을 보여 줍니다. 다른.NET 언어에서 호출 svcutil.exe를 통해 웹 서비스에 액세스 하는 코드를 생성의 웹 참조를 추가 하 여 예를 들어 C# 프로젝트 또는 svcutil.exe를 대신 호출 하도록 Visual Studio 가져오려면. F #에서 WsdlService 형식을 만드는 코드를 작성 하므로 빨리 있습니다 WSDL 형식 공급자를 사용 하 여 추가 옵션을 사용할 형식을 생성 되어 사용할 수 있게 합니다. 이 프로세스는 서비스를 사용할 수 있는 코드를 작성 하는 경우에 의존 합니다.

이 연습에서는 다음 작업을 수행합니다. 이 연습을 완료 하려면이 순서 대로 해당를 완료 해야 합니다.


- 프로젝트 만들기
<br />

- 형식 공급자 구성
<br />

- 웹 서비스를 호출 하 고 결과 처리
<br />


## <a name="creating-the-project"></a>프로젝트 만들기
단계에서 프로젝트를 만들고 WSDL 형식 공급자를 사용 하려면 적절 한 참조를 추가 합니다.


#### <a name="to-create-and-set-up-an-f-project"></a>F# 프로젝트를 만들고 설정하려면

1. 새 F # 콘솔 응용 프로그램 프로젝트를 엽니다.
<br />

2. **솔루션 탐색기**, 프로젝트의에 대 한 바로 가기 메뉴를 열고 **참조** 노드를 선택한 후 **참조 추가**합니다.
<br />

3. 에 **어셈블리** 영역에서 선택 **프레임 워크**, 한 다음 사용할 수 있는 어셈블리의 목록에서 선택 **System.Runtime.Serialization** 및  **System.ServiceModel**합니다.
<br />

4. 에 **어셈블리** 영역에서 선택 **확장**합니다.
<br />

5. 사용할 수 있는 어셈블리의 목록에서 선택 **FSharp.Data.TypeProviders**를 선택한 후는 **확인** 이러한 어셈블리에 대 한 참조를 추가 하는 단추입니다.
<br />

## <a name="configuring-the-type-provider"></a>형식 공급자 구성
이 단계에서는 WSDL 형식 공급자를 사용 하 여 TerraServer 웹 서비스에 대 한 형식을 생성 합니다.


#### <a name="to-configure-the-type-provider-and-generate-types"></a>형식 공급자를 구성하고 형식을 생성하려면

1. 형식 공급자 네임 스페이스를 여는 코드를 다음 줄을 추가 합니다.
<br />

```fsharp
open System
open System.ServiceModel
open Microsoft.FSharp.Linq
open Microsoft.FSharp.Data.TypeProviders
```

2. 웹 서비스와 형식 공급자를 호출 하는 코드의 다음 줄을 추가 합니다. 이 예제에서는 TerraServer 웹 서비스를 사용 합니다.
<br />

```fsharp
type TerraService = WsdlService<" HYPERLINK "https://terraserver-usa.com/TerraService2.asmx?WSDL" https://msrmaps.com/TerraService2.asmx?WSDL">
```

  빨간색 물결 서비스 URI의 철자가 잘못 된 경우 또는 서비스 자체 작동이 중지 되었거나 작동 하지 않을 경우이 코드 줄 아래에 나타납니다. 코드를 가리키는 경우 오류 메시지가 문제를 설명 합니다. 동일한 정보를 찾을 수 있습니다는 **오류 목록** 창 또는 **출력 창** 구성한 후에 있습니다.
<br />  프로젝트에 대 한 app.config 파일을 사용 하 여 또는 공급자 형식 선언에 정적 형식 매개 변수를 사용 하 여 WSDL 연결에 대 한 구성 설정을 지정 하는 방법은 두 가지가 있습니다. Svcutil.exe를 사용 하 여 적절 한 구성 파일 요소를 생성할 수 있습니다. Svcutil.exe를 사용 하 여 웹 서비스에 대 한 구성 정보를 생성 하는 방법에 대 한 자세한 내용은 참조 [ServiceModel Metadata 유틸리티 도구 &#40; Svcutil.exe &#41; ](https://msdn.microsoft.com/library/aa347733.aspx). 에 대 한 전체 설명은 WSDL 형식 공급자에 대 한 정적 형식 매개 변수를 참조 하세요. [WsdlService 형식 공급자](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d)합니다.
<br />

## <a name="calling-the-web-service-and-processing-the-results"></a>웹 서비스를 호출 하 고 결과 처리
각 웹 서비스에 고유한 집합이 해당 메서드 호출에 대 한 매개 변수로 사용 되는 형식. 이러한 매개 변수를 준비 합니다.이 단계에서는 웹 메서드를 호출 하 고 반환 되는 정보를 처리 합니다.


#### <a name="to-call-the-web-service-and-process-the-results"></a>웹 서비스를 호출 하 고 결과 처리 하려면

1. 웹 서비스의 시간이 초과 될 수 있습니다 또는 작동 하지 않으므로 예외를 처리 하는 블록에 웹 서비스 호출을 포함 해야 합니다. 웹 서비스에서 데이터를 가져올 다음 코드를 작성 합니다.
<br />

```fsharp
try
  let terraClient = TerraService.GetTerraServiceSoap ()
  let myPlace = new TerraService.ServiceTypes.msrmaps.com.Place(City = "Redmond", State = "Washington", Country = "United States")
  let myLocation = terraClient.ConvertPlaceToLonLatPt(myPlace)
  printfn "Redmond Latitude: %f Longitude: %f" (myLocation.Lat) (myLocation.Lon)
with
| :? ServerTooBusyException as exn ->
  let innerMessage =
    match (exn.InnerException) with
    | null -> ""
    | innerExn -> innerExn.Message
  printfn "An exception occurred:\n %s\n %s" exn.Message innerMessage
| exn -> printfn "An exception occurred: %s" exn.Message
```

와 같은 웹 서비스에 필요한 데이터 종류를 만들 **위치** 및 **위치**는 WsdlService 아래 중첩된 형식 유형으로, **TerraService**합니다.
<br />


## <a name="see-also"></a>참고 항목
[WsdlService 형식 공급자](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d)

[형식 공급자](index.md)
