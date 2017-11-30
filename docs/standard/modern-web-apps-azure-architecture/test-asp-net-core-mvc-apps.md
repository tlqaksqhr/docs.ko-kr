---
title: "ASP.NET Core MVC 응용 프로그램 테스트"
description: "ASP.NET Core와 Azure의 최신 웹 응용 프로그램을 설계 | ASP.NET Core MVC 응용 프로그램 테스트"
author: ardalis
ms.author: wiwagn
ms.date: 10/08/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 4611ffa8334e124946e849306d3281b695830eb1
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2017
---
# <a name="test-aspnet-core-mvc-apps"></a>ASP.NET Core MVC 응용 프로그램 테스트

> _"단위 테스트 제품, 마음에 들지 않으면 가능성이 고객 않습니다 하려고 하거나, 테스트 합니다."_
> _-익명-

## <a name="summary"></a>요약

복잡성에 관계 없이 소프트웨어 변경 사항에 따라 예기치 않은 방법으로 실패할 수 있습니다. 따라서 변경을 수행한 후 테스트는 가장 간단한 (또는 최소 중요) 응용 프로그램을 제외 반드시 필요 합니다. 소프트웨어 테스트 수동 테스트는 가장 느린 이상 안정적이 고 가장 비용이 많이 드는 방식입니다. 그러나 응용 프로그램 테스트 가능 이어야 하도록 설계 되지 않은, 사용할 수 있는 유일한 수단 수 있습니다. 아키텍처 원칙으로 배치 하는 다음 장에서 X 작성 된 응용 프로그램 단위 테스트를 수행할 수 있어야 합니다. 및 자동화 된 통합 및 기능 테스트 에서도 ASP.NET Core 응용 프로그램을 지원 합니다.

## <a name="kinds-of-automated-tests"></a>자동화 된 테스트의 종류

소프트웨어 응용 프로그램에 대 한 자동화 된 테스트의 여러 가지 있습니다. 가장 단순한 가장 낮은 수준의 테스트는 단위 테스트 합니다. 약간 더 높은 수준에서은 통합 테스트 및 기능 테스트입니다. 다른 종류의 UI 테스트, 부하 테스트, 스트레스 테스트 및 스모크 테스트와 테스트,이 문서의 다루지 않습니다.

### <a name="unit-tests"></a>단위 테스트

단위 테스트 응용 프로그램 논리의 단일 부분을 테스트합니다. 더 이상 그럴 것 중 일부를 나열 하 여 설명할 수 있습니다 하나. 단위 테스트에 대 한 종속성 또는 인프라-어떤 통합 테스트를 사용자 코드가 작동 하는 방법을 테스트 하지 않습니다. 단위 테스트에서 코드가 작성 되는 프레임 워크를 테스트 하지 않는-것 작동 하거나, 하는 경우 하지 않습니다, 버그 및 해결 방법을 코드 가정해 야 합니다. 단위 테스트 프로세스 및 메모리에 완전히 실행 됩니다. 파일 시스템, 네트워크 또는 데이터베이스와 통신 하지 않는 것입니다. 단위 테스트 에서만 코드를 테스트 해야 합니다.

단위 테스트 코드, 외부 종속성이 없고 단일 단위만 테스트 사실로 매우 빠르게 실행 해야 합니다. 따라서 몇 초 후에 수백 개의 단위 테스트의 테스트 도구 모음을 실행할 수 있습니다. 자주 이상적으로 모든 자동화 된 빌드 및 확실히 공유 소스 제어 리포지토리에 모든 푸시하기 전에 실행할 빌드 서버에 있습니다.

### <a name="integration-tests"></a>통합 테스트

데이터베이스와 파일 시스템 등의 인프라와 상호 작용 하 여 코드를 캡슐화 하는 아니지만 하면는 해당 코드의 일부 및 여전히 테스트 하려고 할 수 있습니다. 또한 응용 프로그램의 종속성은 완벽 하 게 해결 하는 경우 예상 대로 코드의 계층 상호 작용 있는지 확인 해야 합니다. 통합 테스트의 책임입니다. 통합 테스트는 종종 외부 종속성 및 인프라에 따라 달라 지므로 느리고 보다 단위 테스트를 설정 하는 것이 어려울 경우가 많습니다. 따라서 통합 테스트에서 단위 테스트를 사용 하 여 테스트 될 수 있는 작업을 테스트 하면 안 됩니다. 단위 테스트와 함께 지정된 된 시나리오를 테스트 하려면 하는 경우 단위 테스트와 함께 테스트 해야 합니다. 수 없는 다음 통합 테스트를 사용 하십시오.

통합 테스트는 더 복잡 한 설치 및 단위 테스트 보다 해체 프로시저 경우가 있습니다. 예를 들어 실제 데이터베이스에 대해 이동 하는 통합 테스트를 각 테스트 실행 하기 전에 알려진된 상태로 데이터베이스를 반환 하는 방법이 필요 합니다. 새 테스트 추가 되 고 프로덕션 데이터베이스 스키마 진화 함에 따라 이러한 테스트 스크립트의 크기와 복잡성 증가 경향이 있습니다. 많은 큰 시스템에서 공유 소스 제어에 대 한 변경 내용 체크 인 하기 전에 개발자 워크스테이션에 통합 테스트의 전체 제품군을 실행 하기에 적합 아닙니다. 이러한 경우에는 빌드 서버에서 통합 테스트를 실행할 수 있습니다.

LocalFileImageService 구현 클래스 인출 및 id를 지정 하는 특정 폴더에서 이미지 파일의 바이트를 반환 하기 위한 논리를 구현 합니다.

```cs
public class LocalFileImageService : IImageService
{
    private readonly IHostingEnvironment _env;
    public LocalFileImageService(IHostingEnvironment env)
    {
        _env = env;
    }
    public byte[] GetImageBytesById(int id)
    {
        try
        {
            var contentRoot = _env.ContentRootPath + "//Pics";
            var path = Path.Combine(contentRoot, id + ".png");
            return File.ReadAllBytes(path);
```

### <a name="functional-tests"></a>기능 테스트

통합 테스트 시스템의 일부 구성 요소가 올바르게 작동 하는지 함께 확인 하는 개발자의 관점에서 기록 됩니다. 기능 테스트는 사용자의 관점에서 작성 하 고 해당 요구 사항에 따라 시스템의 정확성을 확인 합니다. 다음 발췌 구문에서는 단위 테스트에 비해 기능 테스트에 대해 생각 하는 방법에 대 한 유용한 예를 들어를 제공 합니다.

> "개발 시스템을 여러 번 건물 집에 비유할 됩니다. 이 비유 매우 올바르지 않으면 하는 동안 그에 따라 확장할 수 단위 테스트 및 테스트 기능 간의 차이점을 이해할 수 있도록 합니다. 단위 테스트는 주택 생성 사이트를 방문 하는 빌딩 검사기과 같습니다. 그는 집 기반 프레이밍, 전자, 배관, 및 등의 다양 한 내부 시스템 데 사용 합니다. 그 집의 부분 제대로 작동 되며을 안전 하 게 빌드 코드, 즉 충족 (테스트)를 확인 합니다. 이 시나리오에서 기능 테스트는이 동일한 구성 사이트를 방문 주택 소유자와 유사 합니다. 그 가정 내부 시스템은 적절 하 게 동작, 구성 관리자에서 자신의 작업을 수행 합니다. 주택 소유자는 어떤는 것 처럼이 집에서에 포커스가 있습니다. 그 집을 표시 되는 모양을를 우려, 능숙 크기 대화방에서는 다양 한, 집 가족의 요구에 맞게지 않습니다, 그리고에 적합 한 지점이 아침 sun를 catch 하는 창. 주택 소유자는 실행 하는 기능 테스트 집 합니다. 그 사용자의 관점을가지고 있습니다. 건물 검사기는 집에서 단위 테스트를 수행 합니다. 그에 작성기의 관점입니다. "

원본: [단위 기능 테스트 및 테스트](http://www.softwaretestingtricks.com/2007/01/unit-testing-versus-functional-tests.html)

저는 라는 것을 선호 "개발자 두 가지 방법으로 실패: 잘못 된 작업을 만들었습니다 또는 잘못 된 내용을 빌드합니다." 단위 테스트 항목 오른쪽을 작성 하는 확인 기능 테스트 올바른 작업을 작성 하는 것을 확인 합니다.

기능 테스트 시스템 수준에서 작동 하므로 어느 정도의 UI 자동화 필요할 수 있습니다. 일반적으로 통합 테스트와 같은 일부 종류의 테스트 인프라도 함께 작동합니다. 따라서 느리고 단위 및 통합 테스트 보다 더욱 불안정 합니다. 만 있어야 사용자가 예상 대로 작동 하는 시스템 확신 하는 데 필요한 만큼의 기능 테스트.

### <a name="testing-pyramid"></a>피라미드형 테스트

그림 9-1에는 예가 나와 테스트 피라미드에 대 한 Martin Fowler 썼습니다.

![](./media/image9-1.png)

그림 9-1이 피라미드를 테스트 합니다.

피라미드형 및 해당 상대 크기의 다른 계층에 다른 종류를의 테스트 및 개수를 작성 해야 응용 프로그램에 대 한 나타냅니다. 볼 수 있듯이 기능 테스트는 더 작은 계층으로 통합 테스트의 더 작은 계층에서 지원 되는 단위 테스트의 큰 자료가 있어야 하는 것이 좋습니다. 각 계층 이상적 있어야 테스트의 하위 계층에 적절 하 게 수행할 수 없는 것입니다. 특정 시나리오에 필요한 테스트의 종류를 결정 하려고 시도할 때 테스트 피라미드형을 염두에 두십시오.

### <a name="what-to-test"></a>테스트에 어떻게

자동화 된 테스트를 작성 한 경험이 있는 개발자를 위한 일반적인 문제에 나오는 사용 하 여 테스트 합니다. 좋은 출발점 조건부 논리를 테스트 하는 것입니다. 조건문에 따라 변경 하는 동작을 사용 하 여 메서드 있는 모든 곳 (if else 전환, 등)는 적어도 두 가지 특정 조건에 대 한 올바른 동작을 확인 하는 테스트를 수행할 수 있습니다. 코드 오류 조건에 경우 쓰는 데 오류), (없이 코드를 통해 "정상 경로"에 대 한 테스트를 하나 이상 및 "sad 경로"에 대 한 테스트를 하나 이상 (오류나 불규칙 결과) 응용 프로그램의 오류에 관계 없이 예상 대로 동작을 확인 하는 것입니다. 마지막으로, 코드 검사 같은 메트릭이에 집중 하는 것이 아니라 작업이 실패할 수 있는 테스트에 집중 하려고 합니다. 더 많은 코드 검사는 일반적으로 보다 적습니다. 그러나 매우 복잡 하 고 비즈니스에 중요 한 방법의 몇 가지 더 많은 테스트를 작성 하는 일반적으로 테스트 코드 검사 메트릭을 향상 하기 바로 자동 속성에 대 한 테스트를 작성 하는 보다 잘 활용할 시간입니다.

## <a name="organizing-test-projects"></a>테스트 프로젝트를 구성합니다.

하지만 사용자에 대 한 가장 잘 작동 테스트 프로젝트를 구성할 수 있습니다. 테스트 유형 (단위 테스트, 통합 테스트) 및로 (프로젝트, 네임 스페이스)에서 테스트 중인 기능으로 구분 하는 것이 좋습니다. 이러한 분리는 단일 테스트 프로젝트 또는 여러 테스트 프로젝트 내에서 폴더 구성 되는지 여부를 디자인 결정입니다. 한 프로젝트는 가장 간단한 하지만 많은 테스트의 경우 또는 여러 테스트 집합에 더 쉽게 실행 하기 위해 대규모 프로젝트에 대 한 여러 다른 테스트 프로젝트 해야 할 수 있습니다. 많은 팀 응용 프로그램의 여러 프로젝트와 함께 테스트 프로젝트의 많은 여전히 분리 하 여 이러한 각 프로젝트에는 어떤 종류의 테스트에 따라 하는 경우에 특히 될 수 있습니다, 테스트 중인 프로젝트를 기반으로 테스트 프로젝트를 구성 합니다. 테스트 중인 프로젝트 (및 클래스)을 나타내기 위해 테스트 프로젝트 내에 폴더와 응용 프로그램 별로 테스트 당 프로젝트가 두 개 있는 하 손상 방법이입니다.

일반적인 방법은 'src' 폴더에서 응용 프로그램 프로젝트 및 병렬 '테스트' 폴더에서 응용 프로그램의 테스트 프로젝트를 구성 하는 것입니다. 이 조직 유용를 찾을 경우 Visual Studio에서 일치 하는 솔루션 폴더를 만들 수 있습니다.

![](./media/image9-2.png)

솔루션에 테스트 조직 그림 9-2

원하는 어떤 테스트 프레임 워크를 사용할 수 있습니다. XUnit 프레임 워크는 제대로 작동 하 고는 모든 ASP.NET 코어 및 EF 코어 테스트로 작성 됩니다. 그림 9-3에서 나 CLI dotnet 새 xunit를 사용 하 여 표시 된 템플릿을 사용 하 여 Visual Studio에서 xUnit 테스트 프로젝트를 추가할 수 있습니다.

![](./media/image9-3.png)

그림 9-3 Visual Studio에서 테스트 프로젝트는 xUnit 추가

### <a name="test-naming"></a>테스트 이름 지정

각 테스트에서 수행 하는 작업을 나타내는 이름으로 테스트를 일관성 있게에서 필드 이름을 지정 해야 합니다. 유용한 작업을 완료 했습니다 한 가지 방법은 클래스 및 테스트 하는 방법에 따라 테스트 클래스 이름입니다. 이 인해 많은 소형 테스트 클래스 되지만 매우 어떤 각 테스트에 대 한 책임이 선택을 취소 합니다. 클래스 및 메서드를 테스트를 식별 하도록 설정 하는 테스트 클래스 이름으로 테스트 메서드 이름은 테스트 중인 동작을 지정 하 사용할 수 있습니다. 여기에 예상 되는 동작 및 입력 또는이 동작을 생성 해야 하는 가정을 포함 됩니다. 일부 예제 테스트 이름:

-   CatalogControllerGetImage.CallsImageServiceWithId

-   CatalogControllerGetImage.LogsWarningGivenImageMissingException

-   CatalogControllerGetImage.ReturnsFileResultWithBytesGivenSuccess

-   CatalogControllerGetImage.ReturnsNotFoundResultGivenImageMissingException

각 테스트 클래스 이름 "은"를 종료 하 고는 시제를 약간 수정 하는이 방법의 변형:

-   CatalogControllerGetImage**해야**. **호출**ImageServiceWithId

-   CatalogControllerGetImage**해야**. **로그**WarningGivenImageMissingException

일부 팀 더 명확 하 게, 두 번째 명명 방식의 찾을 하지만 약간 더 자세한 정보. 어떤 경우 든, 어떤 경우 실패 한 이름이 확실는 하나 이상의 테스트가 실패 하는 테스트 동작에 대 한 정보를 제공 하는 명명 규칙을 사용 하도록 시도 합니다. 지정 하지 있습니다 테스트 말에 왠지, ControllerTests.Test1, 등으로 테스트 결과에 표시 되 면 값이 없는 제공.

위의 하는 다 수의 작은 테스트 클래스를 생성 합니다. 같은 명명 규칙을 지키는 인지 폴더 및 네임 스페이스를 사용 하 여 테스트를 추가로 구성 하는 것이 좋습니다. 그림 9-4를 테스트 하 여 여러 테스트 프로젝트 내에 폴더를 구성 하는 한 가지 방법을 보여 줍니다.

![](./media/image9-4.png)

**그림 9-4입니다.** 테스트 중인 클래스에 기반 하는 폴더에서 테스트 클래스를 구성 합니다.

물론, 특정 응용 프로그램 클래스에는 테스트 중인 많은 메서드 (및 따라서 여러 테스트 클래스) 하는 경우 이러한 응용 프로그램 클래스에 해당 하는 폴더에 배치 하는 의미를 하면 됩니다. 이 구조는 폴더를 다른 위치에 파일을 구성할 수 차이가 없습니다. 최대 3 개까지 또는 다른 많은 파일이 포함 된 폴더의 파일 관련 4 개, 경우에 자신의 하위 폴더로 이동 하는 것이 도움이 대개 합니다.

## <a name="unit-testing-aspnet-core-apps"></a>단위 테스트 ASP.NET Core 응용 프로그램

잘 설계 된 ASP.NET Core 응용 프로그램에서 대부분의 복잡성 및 비즈니스 논리, 비즈니스 엔터티 및 다양 한 서비스에 캡슐화 됩니다. ASP.NET Core MVC 응용 프로그램 자체, 컨트롤러, 필터, viewmodel, 및 보기와 거의 단위 테스트 해야 합니다. 대부분의 기능에 지정된 된 동작의 작업 메서드 자체 외부에 있습니다. 라우팅이 올바르게 작동 하는지 여부를 테스트 또는 전역 오류 처리 단위 테스트와 함께 효과적으로 수행할 수 없습니다. 마찬가지로, 모든 모델 유효성 검사 및 인증을 포함 하 여 필터 및 권한 부여 필터 단위 테스트를 수행할 수 없습니다. 대부분의 작업 메서드는 동작의 이러한 소스는 없이 다르거나 일반적으로 작은 자신의 작업을 독립적으로 컨트롤러를 사용 하 여 테스트할 수 있는 서비스의 대부분을 위임 해야 합니다.

경우에 따라 리팩터링 코드에 단위 테스트에 정렬 해야 합니다. 자주이 추상화를 식별 하며 종속성 주입을 사용 하 여 추상화를 테스트 하려는 코드에 액세스 하는 대신 인프라에 대 한 직접 코딩 해야 합니다. 예를 들어 이미지를 표시 하기 위한이 간단한 작업 메서드:

```cs
[HttpGet("[controller]/pic/{id}")]
public IActionResult GetImage(int id)
{
    var contentRoot = _env.ContentRootPath + "//Pics";
    var path = Path.Combine(contentRoot, id + ".png");
    Byte[] b = System.IO.File.ReadAllBytes(path);
    return File(b, "image/png");
}
```

단위 테스트이 메서드는 사용 하 여 파일 시스템에서 읽을 수 있는 System.IO.File에 종속 되기 직접 어려운 때문입니다. 예상 대로 작동 하지만 실제 파일에 게 그렇게는 통합 테스트를 확인 하도록이 동작을 테스트할 수 있습니다. 이 메서드의 경로 테스트할 수 없습니다-이 기능을 테스트 곧 수행 하는 방법을 표시 됩니다.

에 직접 단위 테스트 파일 시스템 동작이 수 없는 경우 경로 테스트할 수 없습니다 이란 있는 테스트 하려면 단위 테스트를 가능 하 게 하려면 리팩터링 후 몇 가지 테스트 사례 및 오류 처리 등의 누락 된 동작을 검색할 수 있습니다. 메서드가 수행 하는 파일을 찾을 수 없을 때 수행 해야 하는 것? 이 예제에서는 여 리팩터링된 메서드는 다음과 같이 보입니다.

```cs
[HttpGet("[controller]/pic/{id}")\]
public IActionResult GetImage(int id)
{
    byte[] imageBytes;
    try
    {
        imageBytes = _imageService.GetImageBytesById(id);
    }
    catch (CatalogImageMissingException ex)
    {
        _logger.LogWarning($"No image found for id: {id}");
        return NotFound();
    }
    return File(imageBytes, "image/png");
}
```

\_로 거 및 \_imageService은 둘 다 종속성으로 삽입 됩니다. 에 전달 된 동작 메서드에 전달 되는 동일한 id를 테스트할 수 이제는 \_imageService, 결과 바이트는 FileResult의 일부로 반환 되는 및입니다. 또한 및 테스트할 수 있습니다 예상 대로 오류 로깅을 수행 중인을 이미지가 누락 되었거나, 경우 NotFound 결과가 반환 됩니다 이것은 중요 한 응용 프로그램 동작 (즉,: 방금 일시적인 코드 문제 진단에 추가 하는 개발자) 것으로 가정 합니다. 실제 파일 논리는 별도 구현 서비스 옮겼습니다 및 누락 된 파일의 경우에 대 한 응용 프로그램별 예외를 반환 하도록가 확장 되었습니다. 있습니다 수이 구현 독립적으로 테스트할 통합 테스트를 사용 하 여 합니다.

## <a name="integration-testing-aspnet-core-apps"></a>ASP.NET Core 앱을 테스트 하는 통합

```cs
    }
        catch (FileNotFoundException ex)
        {
            throw new CatalogImageMissingException(ex);
        }
    }
}
```

이 서비스는 별도 서비스로 리팩터링 되기 전의 코드 CatalogController와 마찬가지로 IHostingEnvironment를 사용 합니다. IHostingEnvironment를 사용 하는 컨트롤러의 유일한 코드가 이것이 이후 해당 종속성 CatalogController의 생성자에서 제거 되었습니다.

이 서비스가 올바르게 작동을 테스트 하려면 테스트 알려진된 이미지 파일을 만들고 서비스는 특정 입력이 제공 하는 것을 반환 하는지 확인 해야 합니다. 실제로에 (이 경우 파일 시스템에서 읽기) 테스트 하려는 동작에 모의 개체를 사용 하지 않는 주의 해야 합니다. 그러나 모의 개체 여전히 통합 테스트를 설정 하려면 유용할 수 있습니다. 이 경우 테스트 이미지에 대 한 사용 하려는 폴더를 가리키도록 해당 ContentRootPath IHostingEnvironment 모의 수 있습니다. 전체 작업 통합 테스트 클래스는 다음과 같습니다.

```cs
public class LocalFileImageServiceGetImageBytesById
{
    private byte[] _testBytes = new byte[] { 0x01, 0x02, 0x03 };
    private readonly Mock<IHostingEnvironment> _mockEnvironment = new Mock<IHostingEnvironment>();
    private int _testImageId = 123;
    private string _testFileName = "123.png";
    public LocalFileImageServiceGetImageBytesById()
    {
        // create folder if necessary
        Directory.CreateDirectory(Path.Combine(GetFileDirectory(), "Pics"));
        string filePath = GetFilePath(_testFileName);
        System.IO.File.WriteAllBytes(filePath, _testBytes);
        _mockEnvironment.SetupGet<string>(m => m.ContentRootPath).Returns(GetFileDirectory());
    }
    private string GetFilePath(string fileName)
    {
        return Path.Combine(GetFileDirectory(), "Pics", fileName);
        }
            private string GetFileDirectory()
        {
            var location = System.Reflection.Assembly.GetEntryAssembly().Location;
            return Path.GetDirectoryName(location);
        }

        [Fact]
        public void ReturnsFileContentResultGivenValidId()
        {
            var fileService = new LocalFileImageService(_mockEnvironment.Object);
            var result = fileService.GetImageBytesById(_testImageId);
            Assert.Equal(_testBytes, result);
        }
    }
```

> [!NOTE]
> 테스트 자체는 매우 간단한 코드의 대부분 해야 하는 시스템을 구성 하 고이 경우는 실제 파일에 디스크에서 읽어야 하는 테스트 인프라를 만듭니다. 단위 테스트 보다 더 복잡 한 설치 작업이 필요할 수 있는 통합 테스트에 대 한 일반입니다.

## <a name="functional-testing-aspnet-core-apps"></a>기능 테스트 ASP.NET Core 응용 프로그램

ASP.NET Core 응용 프로그램에 대 한 TestServer 클래스를 사용 하면 기능 테스트 상당히 쉽게 작성할 수 있습니다. 와 마찬가지로 일반적으로 응용 프로그램에 대 한 WebHostBuilder를 사용 하 여 TestServer를 구성 합니다. 이 WebHostBuilder 응용 프로그램의 실제 호스트와 동일 하 게 구성 해야 하지만 더 쉬운 테스트 환경의 모든 측면을 수정할 수 있습니다. 대부분의 경우 캡슐화 할 수 있습니다 (아마도 기본 클래스)에서 다시 사용할 수 있는 메서드 하므로 많은 테스트 사례에 대 한 동일한 TestServer를 재사용 합니다.

```cs
public abstract class BaseWebTest
{
    protected readonly HttpClient _client;
    protected string _contentRoot;

    public BaseWebTest()
    {
        _client = GetClient();
    }
    
    protected HttpClient GetClient()
    {
        var startupAssembly = typeof(Startup).GetTypeInfo().Assembly;
        _contentRoot = GetProjectPath("src", startupAssembly);
        var builder = new WebHostBuilder()
        .UseContentRoot(_contentRoot)
        .UseStartup&lt;Startup&gt;();
        var server = new TestServer(builder);
        var client = server.CreateClient();
        return client;
    }
}
```

GetProjectPath 메서드는 단순히 웹 프로젝트 (샘플 솔루션 다운로드)에 실제 경로 반환합니다. WebHostBuilder이 경우 단순히 지정 위치에서 웹 응용 프로그램에 대 한 콘텐츠 루트 이며, 실제 웹 응용 프로그램에서 동일한 시작 클래스를 참조 합니다. TestServer를 사용 하 여 요청을 만드는 표준 System.Net.HttpClient 유형을 사용 합니다. TestServer는 TestServer에서 실행 중인 응용 프로그램에 요청을 준비 하는 미리 구성 된 클라이언트를 제공 하는 것이 도움이 CreateClient 메서드를 노출 합니다. 이 클라이언트를 사용 하 여 (보호 된 설정 \_위의 기본 테스트에 대 한 클라이언트 멤버가) ASP.NET Core 응용 프로그램에 대 한 기능 테스트를 작성할 때:

```cs
public class CatalogControllerGetImage : BaseWebTest
{
    [Fact]
    public async Task ReturnsFileContentResultGivenValidId()
    {
        var testFilePath = Path.Combine(_contentRoot, "pics//1.png");
        var expectedFileBytes = File.ReadAllBytes(testFilePath);
        var response = await _client.GetAsync("/catalog/pic/1");
        response.EnsureSuccessStatusCode();
        var streamResponse = await response.Content.ReadAsStreamAsync();
        byte[] byteResult;
        using (var ms = new MemoryStream())
        {
            streamResponse.CopyTo(ms);
            byteResult = ms.ToArray();
        }
        Assert.Equal(expectedFileBytes, byteResult);
    }
}
```

모든 미들웨어, 필터, 바인더, 현재 위치에 있을 수 있는 등을 포함 하 여 전체 ASP.NET Core MVC 응용 프로그램 스택을 실행 하는이 기능을 테스트 합니다. 인지 확인 한 경로 지정 ("/ 1/pic 카탈로그 /") 알려진된 위치에 파일에 대 한 예상된 바이트 배열을 반환 합니다. 실제 웹 서버를 설정 하지 않고이 작업을 수행 하 고 있으므로 대부분의 실제 웹을 사용 하 여 테스트를 위해 서버 (예: 방화벽 설정에 문제가) 발생할 수 있는 오류를 방지 합니다. TestServer에 대해 실행 되는 기능 테스트 통합 및 단위 테스트의 경우 보다 일반적으로 느린 있지만 테스트 웹 서버에 네트워크를 통해 실행 되는 테스트 보다 훨씬 빠릅니다.

>[!div class="step-by-step"]
[이전] [다음] (개발-프로세스-에-azure.md) (work-with-data-in-asp-net-core-apps.md)
