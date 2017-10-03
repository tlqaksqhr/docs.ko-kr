---
title: "Windows 컨테이너로 레거시 모놀리식 .NET Framework 응용 프로그램 마이그레이션"
description: "컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | Windows 컨테이너로 레거시 모놀리식 .NET Framework 응용 프로그램 마이그레이션"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.translationtype: HT
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: 1756ff0f49d9bb243fa561ba760418eba79de1f0
ms.contentlocale: ko-kr
ms.lasthandoff: 09/05/2017

---
# <a name="migrating-legacy-monolithic-net-framework-applications-to-windows-containers"></a>Windows 컨테이너로 레거시 모놀리식 .NET Framework 응용 프로그램 마이그레이션

*Windows 컨테이너는 개발 및 테스트 환경을 향상하는 방법 및 Web* *Forms와 같은 레거시 .NET Framework 기술을 기반으로 하는 응용 프로그램을 배포하는 방법으로 사용할 수 있습니다. 이러한 방식으로 레거시 응용 프로그램에 컨테이너를 사용하는 것을 “리프트 앤 시프트” 시나리오라고 합니다.*

이 가이드의 이전 섹션에서는 비즈니스 응용 프로그램이 각각 소규모의 집중적인 서비스를 실행하는 서로 다른 컨테이너 사이에 배포되는 마이크로 서비스 아키텍처를 긍정적으로 설명했습니다. 그 목표에는 많은 이점이 있습니다. 새로운 개발에서는 이러한 접근 방식을 적극적으로 권장합니다. 또한 엔터프라이즈에 중요한 응용 프로그램은 아키텍처 및 구현을 다시 수행하는 비용을 감수할 수 있을 만큼 충분히 유익합니다.

그러나 일부 응용 프로그램은 비용을 감수할 정도로 충분히 유익하지 않습니다. 그렇다고 해서 해당 응용 프로그램을 컨테이너 시나리오에서 사용할 수 없다는 의미는 아닙니다.

이 섹션에서는 그림 7-1에 나와 있는 eShopOnContainers 응용 프로그램을 살펴보겠습니다. 이 응용 프로그램은 eShopOnContainers 엔터프라이즈 팀의 구성원이 제품 카탈로그를 보고 편집하는 데 사용합니다.

![](./media/image1.png)

**그림 7-1**. Windows 컨테이너의 ASP.NET Web Forms 응용 프로그램(레거시 기술)

이 응용 프로그램은 카탈로그 항목을 찾아보고 수정하는 데 사용하는 Web Forms 응용 프로그램입니다. Web Forms 종속성은 이 응용 프로그램이 Web Forms 없이 다시 작성되지 않고 대신 ASP.NET Core MVC를 사용하지 않는 한 .NET Core에서 실행되지 않는다는 것을 의미합니다. 여러분은 변경 없이 컨테이너에서 이러한 응용 프로그램을 실행하는 방법을 확인할 수 있습니다. 또한 일부 기능이 별도의 마이크로 서비스로 이동되었지만 대부분의 기능은 모놀리식 응용 프로그램에 그대로 남아 있는 하이브리드 모드에서 작업할 수 있도록 최소한의 변경만 수행할 수 있는 방법도 확인할 수 있습니다.

## <a name="benefits-of-containerizing-a-monolithic-application"></a>모놀리식 응용 프로그램을 컨테이너화할 경우의 이점

Catalog.WebForms 응용 프로그램은 eShopOnContainers GitHub 리포지토리(<https://github.com/dotnet/eShopOnContainers>)에 제공됩니다. 이 응용 프로그램은 고가용성 데이터 저장소에 액세스하는 독립 실행형 웹 응용 프로그램입니다. 그렇기는 하지만, 컨테이너에서 응용 프로그램을 실행하면 이점이 있습니다. 응용 프로그램의 이미지를 만들 수 있습니다. 이 시점부터는 모든 배포가 동일한 환경에서 실행됩니다. 모든 컨테이너가 동일한 OS 버전을 사용하며, 동일한 버전의 종속성이 설치되고, 동일한 프레임워크를 사용하며, 동일한 프로세스를 사용하여 빌드됩니다. 그림 7-2에서는 Visual Studio 2017에 로드된 응용 프로그램을 볼 수 있습니다.

![](./media/image2.png)

**그림 7-2**. Visual Studio 2017의 카탈로그 관리 Web Forms 응용 프로그램

또한 개발자는 이 일관된 환경에서 응용 프로그램을 모두 실행할 수 있습니다. 특정 버전에만 나타나는 문제가 스테이징 환경 또는 프로덕션 환경에서는 드러나지 않고 개발자에게 즉시 표시됩니다. 응용 프로그램이 컨테이너에서 실행되면 개발 팀 사이의 개발 환경 간 차이가 덜 중요해집니다.

마지막으로, 컨테이너화된 응용 프로그램은 더욱 수평으로 확장된 곡선을 갖습니다. 컨테이너화된 앱을 통해 어떻게 VM 또는 물리적 컴퓨터에서 더 많은 컨테이너를 사용할 수 있는지에 대해 알아보았습니다. 이는 밀도가 높아지고 필요한 자원이 줄어든다는 것을 의미합니다.

이러한 모든 이유로 “리프트 앤 시프트” 작업을 사용하여 Docker 컨테이너에서 레거시 모놀리식 앱을 실행하는 것이 좋습니다. “리프트 앤 시프트”라는 문구는 작업의 범위를 설명합니다. 즉, 물리적 컴퓨터나 가상 컴퓨터에서 전체 응용 프로그램을 들어 올린(리프트) 후 컨테이너로 옮깁니다(시프트). 이상적인 상황에서는 응용 프로그램 코드를 컨테이너에서 실행하기 위해 해당 코드를 변경할 필요가 없습니다.

## <a name="possible-migration-paths"></a>가능한 마이그레이션 경로

모놀리식 응용 프로그램으로서 Catalog.Webforms 응용 프로그램은 데이터 액세스 라이브러리를 비롯하여 모든 코드가 포함된 하나의 웹 응용 프로그램입니다. 데이터베이스는 별도의 고가용성 컴퓨터에서 실행됩니다. 해당 구성은 모의 ​​카탈로그 서비스를 사용하여 샘플 코드에서 시뮬레이션됩니다. 즉, 해당 모조 데이터에 대해 Catalog.WebForms 응용 프로그램을 실행하여 순수한 리프트 앤 시프트 시나리오를 시뮬레이션할 수 있습니다. 이는 코드를 전혀 변경하지 않고 컨테이너에서 실행하기 위해 기존 자산을 이동하는 가장 간단한 마이그레이션 경로를 보여 줍니다. 이 경로는 마이크로 서비스로 이동할 기능과의 상호 작용을 최소화하는 완전한 응용 프로그램에 적합합니다.

그러나 eShopOnContainers 웹 사이트는 이미 다른 시나리오에 마이크로 서비스를 사용하여 데이터 저장소에 액세스하고 있습니다. 카탈로그 데이터 저장소에 직접 액세스하는 대신 카탈로그 마이크로 서비스를 활용하기 위해 카탈로그 편집기를 추가로 약간 변경할 수 있습니다.

이러한 변경 사항은 고유한 응용 프로그램에 대한 연속을 보여 줍니다. 변경 없이 기존 응용 프로그램을 컨테이너로 이동하는 작업부터 기존 응용 프로그램이 새로운 마이크로 서비스의 일부에 액세스할 수 있도록 약간 변경하는 작업, 새로운 마이크로 서비스 기반 아키텍처에 완벽히 참여하도록 응용 프로그램을 완전히 다시 작성하는 작업에 이르기까지 무엇이든 수행할 수 있습니다. 적절한 경로는 마이그레이션 비용과 마이그레이션의 이점에 따라 달라집니다.

## <a name="application-tour"></a>응용 프로그램 둘러보기

Catalog.WebForms 솔루션을 로드하여 응용 프로그램을 독립 실행형 응용 프로그램으로 실행할 수 있습니다. 이 구성에서는 영구 저장소 데이터베이스 대신 응용 프로그램에서 가짜 서비스를 사용하여 데이터를 반환합니다. 응용 프로그램은 Autofac(<https://autofac.org/>)을 IOC(Inversion of Control) 컨테이너로 사용합니다. DI(종속성 주입)를 사용하면 모조 데이터 또는 라이브 카탈로그 데이터 서비스를 사용하도록 응용 프로그램을 구성할 수 있습니다. (DI에 대해서는 바로 뒤에 더 자세히 설명하겠습니다.) 시작 코드는 web.config 파일에서 useFake 설정을 읽고, 모조 데이터 서비스 또는 라이브 카탈로그 서비스를 주입하도록 Autofac 컨테이너를 구성합니다. web.config 파일에서 useFake를 false로 설정하여 응용 프로그램을 실행하는 경우 Web Forms 응용 프로그램에서 카탈로그 데이터가 표시됩니다.

이 응용 프로그램에서 사용된 대부분의 기술은 Web Forms를 사용하는 모든 사람에게 매우 친숙해야 합니다. 그러나 카탈로그 마이크로 서비스는 일반적으로 친숙하지 않을 수 있는 두 가지 기술을 도입했는데, 이는 바로 앞에서 언급한 DI(종속성 주입) 및 Web Forms의 비동기 데이터 저장소 작업입니다.

DI는 필요한 모든 리소스를 할당하는 클래스를 작성하는 일반적인 개체 지향 전략을 반대로 수행합니다. 대신 클래스가 서비스 컨테이너에서 해당 종속성을 요청합니다. DI의 이점은 외부 서비스를 모조(모의)로 대체하여 테스트 또는 기타 환경을 지원할 수 있다는 것입니다.

DI 컨테이너는 web.config appSettings 구성을 사용하여 모조 카탈로그 데이터를 사용할지 또는 실행 중인 서비스의 라이브 데이터를 사용할지 여부를 제어합니다. 응용 프로그램은 컨테이너를 빌드하는 HttpModule 개체를 등록하고, 종속성을 주입하기 위한 사전 요청 처리기를 등록합니다. 다음 예제와 같이 Modules/AutoFacHttpModule.cs 파일에서 해당 코드를 확인할 수 있습니다.

```cs
private static IContainer CreateContainer()
{
  // Configure AutoFac:
  // Register Containers:

  var settings = WebConfigurationManager.AppSettings;
  var useFake = settings["usefake"];
  bool fake = useFake == "true";
  var builder = new ContainerBuilder();

  if (fake)
  {
    builder.RegisterType<CatalogMockService>()
    .As<ICatalogService>();
  }
  else
  {
    builder.RegisterType<CatalogService>()
    .As<ICatalogService>();
    builder.RegisterType<RequestProvider>()
    .As<IRequestProvider>();
  }

  var container = builder.Build();
  return container;
}

private void InjectDependencies()
{
  if (HttpContext.Current.CurrentHandler is Page page)
  {
    // Get the code-behind class that we may have written
    var pageType = page.GetType().BaseType;

    // Determine if there is a constructor to inject, and grab it
    var ctor = (from c in pageType.GetConstructors()
                where c.GetParameters().Length > 0
                select c).FirstOrDefault();

    if (ctor != null)
    {
      // Resolve the parameters for the constructor
      var args = (from parm in ctor.GetParameters()
                  select Container.Resolve(parm.ParameterType))
                  .ToArray();

      // Execute the constructor method with the arguments resolved
      ctor.Invoke(page, args);
    }

    // Use the Autofac method to inject any
    // properties that can be filled by Autofac
    Container.InjectProperties(page);
  }
}
```

응용 프로그램의 페이지(Default.aspx.cs 및 EditPage.aspx.cs)는 이러한 종속성을 사용하는 생성자를 정의합니다. 기본 생성자가 여전히 있으며 액세스 가능합니다. 인프라에는 다음 코드가 필요합니다.

```cs
protected _Default() { }

public _Default(ICatalogService catalog) => this.catalog = catalog;
```

카탈로그 API는 모두 비동기 메서드입니다. Web Forms는 이제 모든 데이터 컨트롤에 대해 이러한 메서드를 지원합니다. Catalog.WebForms 응용 프로그램은 목록 및 편집 페이지에 모델 바인딩을 사용합니다. 페이지의 컨트롤은 작업 반환 비동기 작업을 지정하는 SelectMethod, UpdateMethod, InsertMethod 및 DeleteMethod 속성을 정의합니다. Web Forms 컨트롤은 컨트롤에 바인딩된 메서드가 비동기적인 경우를 파악합니다. 비동기 select 메서드를 사용할 때 발생하는 유일한 제한은 페이징을 지원할 수 없다는 것입니다. 페이징 시그니처에는 out 매개 변수가 필요하며, 비동기 메서드에는 out 매개 변수가 있을 수 없습니다. 이 같은 기술은 카탈로그 서비스의 데이터가 필요한 다른 페이지에서 사용됩니다.

카탈로그 Web Forms 응용 프로그램의 기본 구성은 catalog.api 서비스의 모의 구현을 사용합니다. 이 모의에서는 해당 데이터에 하드 코드된 데이터 집합을 사용하므로, 개발 환경에서 catalog.api 서비스에 대한 종속성을 제거함으로써 일부 작업이 간소화됩니다.

## <a name="lifting-and-shifting"></a>리프트 앤 시프트 작업

Visual Studio는 응용 프로그램을 컨테이너화하는 데 많은 지원을 제공합니다. 프로젝트 노드를 마우스 오른쪽 단추로 클릭한 후 **추가**, **Docker 지원**을 차례로 선택합니다. Docker 프로젝트 템플릿은 **docker-compose**라는 솔루션에 새 프로젝트를 추가합니다. 그림 7-3과 같이 프로젝트는 필요한 이미지를 구성(또는 빌드)하는 Docker 자산을 포함하고 있으며, 필수 컨테이너를 실행하기 시작합니다.

가장 간단한 리프트 앤 시프트 시나리오에서 응용 프로그램은 Web Forms 응용 프로그램에 사용되는 단일 서비스입니다. 또한 템플릿은 **docker-compose** 프로젝트를 가리키도록 시작 프로젝트를 변경합니다. 이제 Ctrl+F5 또는 F5 키를 누르면 Docker 이미지가 생성되고 Docker 컨테이너가 시작됩니다.

![](./media/image3.png)

**그림 7-3**. Web Forms 솔루션의 **docker-compose** 프로젝트

솔루션을 실행하기 전에 Windows 컨테이너를 사용하도록 Docker를 구성했는지 확인해야 합니다. 그렇게 하려면 그림 7-4와 같이 Windows에서 Docker 작업 표시줄 아이콘을 마우스 오른쪽 단추로 클릭하고 **Windows 컨테이너로 전환**을 선택합니다.

![](./media/image4.png)

**그림 7-4**. Windows의 Docker 작업표시줄 아이콘에서 Windows 컨테이너로 전환

메뉴 항목에 **Linux 컨테이너로 전환**이 표시되면 Windows 컨테이너가 있는 Docker가 이미 실행 중입니다.

솔루션을 실행하면 Docker 호스트가 다시 시작됩니다. 빌드할 때 Web Forms 프로젝트에 대한 응용 프로그램 및 Docker 이미지를 빌드합니다. 처음으로 이 작업을 수행하면 상당한 시간이 걸립니다. 빌드 프로세스가 기본 Windows Server 이미지 및 ASP.NET용 추가 이미지를 가져오기 때문입니다. 후속 빌드 및 실행 주기는 훨씬 빨라집니다.

Docker 프로젝트 템플릿에 의해 추가된 파일에 대해 더 자세히 살펴보겠습니다. 이 템플릿은 여러 파일을 생성합니다. Visual Studio에서는 이러한 파일을 사용하여 Docker 이미지를 만들고 컨테이너를 시작합니다. CLI에서 동일한 파일을 사용하여 Docker 명령을 수동으로 실행할 수 있습니다.

다음 Dockerfile 예제는 ASP.NET 사이트를 실행하는 Windows ASP.NET 이미지를 기반으로 하여 Docker 이미지를 빌드하기 위한 기본 설정을 보여 줍니다.

```
FROM microsoft/aspnet

ARG source

WORKDIR /inetpub/wwwroot

COPY ${source:-obj/Docker/publish} .
```

이 Dockerfile은 Linux 컨테이너에서 ASP.NET Core 응용 프로그램을 실행하기 위해 생성된 것과 매우 비슷해 보입니다. 그러나 몇 가지 중요한 차이점이 있습니다. 가장 중요한 차이는 기본 이미지가 microsoft/aspnet이며, 이는 .NET Framework가 포함된 현재 Windows Server 이미지라는 점입니다. 다른 차이는 소스 디렉터리에서 복사된 디렉터리가 다르다는 점입니다.

**docker-compose** 프로젝트의 기타 파일은 컨테이너를 빌드하고 구성하는 데 필요한 Docker 자산입니다. Visual Studio에서는 다양한 docker-compose.yml 파일을 한 노드 아래에 배치하여 어떻게 사용되는지를 강조 표시합니다. 기본 docker-compose 파일에는 모든 구성에 공통적인 지시문이 포함되어 있습니다. docker-compose.override.yml 파일에는 개발자 구성에 대한 환경 변수 및 관련 재정의가 포함되어 있습니다. .vs.debug 및 .vs.release를 사용하는 변형은 Visual Studio에서 실행 중인 컨테이너에 연결하고 이 컨테이너를 관리할 수 있도록 하는 환경 설정을 제공합니다.

Visual Studio 통합은 솔루션에 Docker 지원을 추가하는 과정의 일부이지만, 이전 섹션에서 살펴보았듯이 docker-compose up 명령을 사용하여 명령줄에서 빌드하고 실행할 수도 있습니다.

## <a name="getting-data-from-the-existing-catalog-net-core-microservice"></a>기존 카탈로그 .NET Core 마이크로 서비스에서 데이터 가져오기

모조 데이터를 사용하는 대신 데이터를 가져오는 데 eShopOnContainers 카탈로그 마이크로 서비스를 사용하도록 Web Forms 응용 프로그램을 구성할 수 있습니다. 이렇게 하려면 web.config 파일을 편집하여 useFake 키의 값을 false로 설정합니다. DI 컨테이너는 하드 코드된 데이터를 반환하는 클래스 대신 라이브 카탈로그 마이크로 서비스에 액세스하는 클래스를 사용합니다. 다른 코드 변경은 필요하지 않습니다.

라이브 카탈로그 서비스에 액세스하려면 **docker-compose** 프로젝트를 업데이트하여 카탈로그 서비스 이미지를 빌드하고 카탈로그 서비스 컨테이너를 시작해야 합니다. Windows용 Docker CE는 Linux 컨테이너와 Windows 컨테이너를 모두 지원하지만, 동시에 지원하지는 않습니다. 카탈로그 마이크로 서비스를 실행하려면 Windows 기반 컨테이너 위에 카탈로그 마이크로 서비스를 실행하는 이미지를 빌드해야 합니다. 이 접근법은 이전 섹션에서 살펴보았던 것과는 다른 마이크로 서비스 프로젝트용 Dockerfile이 필요합니다. Dockerfile.windows 파일은 카탈로그 API 컨테이너 이미지를 빌드하기 위한 구성 설정을 포함하고 있으므로 Windows 컨테이너에서 실행됩니다(예: Windows Nano Docker 이미지를 사용하기 위해).

카탈로그 마이크로 서비스는 SQL Server 데이터베이스를 사용합니다. 따라서 Windows 기반 SQL Server Docker 이미지도 사용해야 합니다.

이러한 변경 이후 docker-compose 프로젝트는 응용 프로그램을 시작하는 데 더 많은 작업을 수행합니다. 이제 프로젝트는 Windows 기반 SQL Server 이미지를 사용하여 SQL Server를 시작하며, Windows 컨테이너에서 카탈로그 마이크로 서비스를 시작합니다. 또한 Windows 컨테이너에서 Web Forms 카탈로그 편집기 컨테이너도 시작합니다. 이미지 중 하나라도 빌드가 필요한 경우 이미지가 먼저 생성됩니다.

## <a name="development-and-production-environments"></a>개발 및 프로덕션 환경

개발 구성과 프로덕션 구성 간에는 몇 가지 차이가 있습니다. 개발 환경에서는 Windows 컨테이너에서 Web Forms 응용 프로그램, 카탈로그 마이크로 서비스 및 SQL Server를 동일한 Docker 호스트의 일부로 실행합니다. 이전 섹션에서 Linux 기반 Docker 호스트의 기타 .NET Core 기반 서비스와 동일한 Docker 호스트에 배포된 SQL Server 이미지에 대해 언급했습니다. 동일한 Docker 호스트(또는 클러스터)에서 여러 마이크로 서비스를 실행하면 네트워크 통신이 줄어들고 컨테이너 간 통신 대기 시간이 짧아지는 이점이 있습니다.

개발 환경에서는 동일한 OS에서 모든 컨테이너를 실행해야 합니다. Windows용 Docker CE는 Windows 기반 컨테이너와 Linux 기반 컨테이너의 실행을 동시에 지원하지 않습니다. 프로덕션 환경에서는 단일 Docker 호스트(또는 클러스터)의 Windows 컨테이너에서 카탈로그 마이크로 서비스를 실행할지 아니면 다른 Docker 호스트의 Linux 컨테이너에서 실행 중인 카탈로그 마이크로 서비스 인스턴스와 Web Forms 응용 프로그램을 통신하도록 설정할지 결정할 수 있습니다. 이는 네트워크 대기 시간을 최적화하려는 방법에 따라 달라집니다. 대부분의 경우 간편한 배포 및 통신 대기 시간 단축을 위해 응용 프로그램에서 사용하는 마이크로 서비스가 동일한 Docker 호스트(또는 Swarm)에서 실행되기를 원합니다. 이러한 구성에서는 마이크로 서비스 인스턴스와 영구 데이터 저장소를 위한 고가용성 서버 간 통신만 유일하게 비용이 많이 듭니다.

>[!div class="step-by-step"]
[이전](../net-core-single-containers-linux-windows-server-hosts/index.md) [다음](../multi-container-microservice-net-applications/index.md)

