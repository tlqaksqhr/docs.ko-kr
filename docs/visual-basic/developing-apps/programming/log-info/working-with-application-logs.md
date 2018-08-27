---
title: Visual Basic에서 응용 프로그램 로그 작업
ms.date: 07/20/2015
helpviewer_keywords:
- logs, application
- application event logs, Visual Basic
- application event logs
ms.assetid: 2581afd1-5791-4bc4-86b2-46244e9fe468
ms.openlocfilehash: c11e1f0c99b3189c7a353e6778c701667b0a1d12
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43000032"
---
# <a name="working-with-application-logs-in-visual-basic"></a>Visual Basic에서 응용 프로그램 로그 작업
`My.Applicaton.Log` 및 `My.Log` 개체를 사용하면 로깅 및 추적 정보를 로그에 쉽게 쓸 수 있습니다.  
  
## <a name="how-messages-are-logged"></a>메시지가 기록되는 방식  
 먼저 로그의 <xref:System.Diagnostics.TraceSource.Switch%2A> 의 <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A> 속성으로 메시지의 심각도를 확인합니다. 기본적으로 심각도가 "정보" 이상인 메시지만 로그의 `TraceListener` 컬렉션에 지정된 추적 수신기로 전달됩니다. 그런 다음 각 수신기는 메시지의 심각도를 수신기의 <xref:System.Diagnostics.TraceSource.Switch%2A> 속성과 비교합니다. 메시지의 심각도가 충분히 높으면 수신기는 메시지를 기록합니다.  
  
 다음 다이어그램에서는 `WriteEntry` 메서드에 기록된 메시지가 로그의 추적 수신기의 `WriteLine` 메서드로 전달되는 방식을 보여 줍니다.  
  
 ![내 로그 호출](../../../../visual-basic/developing-apps/programming/log-info/media/mylogcall.png "MyLogCall")  
  
 응용 프로그램의 구성 파일을 변경하여 로그 및 추적 수신기의 동작을 변경할 수 있습니다. 다음 다이어그램에서는 로그의 각 부분과 구성 파일에서의 해당 위치를 보여 줍니다.  
  
 ![내 로그 구성](../../../../visual-basic/developing-apps/programming/log-info/media/mylogconfig.png "MyLogConfig")  
  
## <a name="where-messages-are-logged"></a>메시지가 기록되는 위치  
 어셈블리에 구성 파일이 없으면 `My.Application.Log` 및 `My.Log` 개체가 <xref:System.Diagnostics.DefaultTraceListener> 클래스를 통해 응용 프로그램의 디버그 출력에 메시지를 기록합니다. 또한 `My.Application.Log` 개체는 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 클래스를 통해 어셈블리의 로그 파일에 기록하고, `My.Log` 개체는 <xref:System.Web.WebPageTraceListener> 클래스를 통해 ASP.NET 웹 페이지의 출력에 기록합니다.  
  
 디버그 출력은 디버그 모드에서 응용 프로그램을 실행할 때 Visual Studio **출력** 창에서 볼 수 있습니다. **출력** 창을 열려면 **디버그** 메뉴 항목을 클릭하고 **창**을 가리킨 다음 **출력**을 클릭합니다. **출력** 창의 **다음에서 출력 보기** 상자에서 **디버그** 를 선택합니다.  
  
 기본적으로 `My.Application.Log` 는 사용자의 응용 프로그램 데이터가 있는 경로에 로그 파일을 씁니다. 경로는 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.FullLogFileName%2A> 개체의 <xref:Microsoft.VisualBasic.Logging.Log.DefaultFileLogWriter%2A> 속성에서 가져올 수 있습니다. 해당 경로의 형식은 다음과 같습니다.  
  
 `BasePath`\\`CompanyName`\\`ProductName`\\`ProductVersion`  
  
 `BasePath` 의 일반적인 값은 다음과 같습니다.  
  
 C:\Documents and Settings\\`username`\Application Data  
  
 `CompanyName`, `ProductName`및 `ProductVersion` 값은 응용 프로그램의 어셈블리 정보에서 가져옵니다. 로그 파일 이름의 형식은 *AssemblyName*.log이며 여기서 *AssemblyName* 은 확장명을 제외한 어셈블리의 파일 이름입니다. 응용 프로그램에서 로그에 쓰려고 할 때 원본 로그를 사용할 수 없는 경우와 같이 둘 이상의 로그 파일이 필요한 경우 로그 파일 이름의 형식은 *AssemblyName*-*iteration*.log이며 여기서 `iteration` 은 양의 `Integer`을 클릭합니다.  
  
 컴퓨터 및 응용 프로그램의 구성 파일을 추가하거나 변경하여 기본 동작을 재정의할 수 있습니다. 자세한 내용은 [Walkthrough: Changing Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)을 참조하십시오.  
  
## <a name="configuring-log-settings"></a>로그 설정 구성  
 `Log` 개체에는 응용 프로그램 구성 파일인 app.config 없이 작동하는 기본 구현이 있습니다. 기본값을 변경하려면 새 설정이 지정된 구성 파일을 추가해야 합니다. 자세한 내용은 [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)을 참조하세요.  
  
 로그 구성 섹션은 app.config 파일의 주 `<system.diagnostics>` 노드에 있는 `<configuration>` 노드에 있습니다. 로그 정보는 다음과 같은 여러 노드에 정의되어 있습니다.  
  
-   `Log` 개체의 수신기는 DefaultSource라는 이름의 `<sources>` 노드에서 정의합니다.  
  
-   `Log` 개체의 심각도 필터는 DefaultSwitch라는 이름의 `<switches>` 노드에서 정의합니다.  
  
-   로그 수신기는 `<sharedListeners>` 노드에서 정의합니다.  
  
 다음 코드에서 `<sources>`, `<switches>`및 `<sharedListeners>` 노드의 예제를 볼 수 있습니다.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="DefaultSource" switchName="DefaultSwitch">  
        <listeners>  
          <add name="FileLog"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="DefaultSwitch" value="Information" />  
    </switches>  
    <sharedListeners>  
      <add name="FileLog"  
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,  
          Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,   
          PublicKeyToken=b03f5f7f11d50a3a, processorArchitecture=MSIL"  
        initializeData="FileLogWriter"  
      />  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="changing-log-settings-after-deployment"></a>배포 후 로그 설정 변경  
 위의 예제에서 볼 수 있는 것처럼 응용 프로그램을 개발할 때 구성 설정은 app.config 파일에 저장됩니다. 응용 프로그램을 배포한 후에도 구성 파일을 편집하여 로그를 구성할 수 있습니다. Windows 기반 응용 프로그램에서 이 파일의 이름은 *applicationName*.exe.config이며 실행 파일과 같은 폴더에 있어야 합니다. 웹 응용 프로그램의 경우 프로젝트와 연결된 Web.config 파일입니다.  
  
 응용 프로그램은 클래스의 인스턴스를 만드는 코드를 처음으로 실행할 때 개체에 대한 정보가 있는지 구성 파일을 검사합니다. `Log` 개체의 경우에는 `Log` 개체에 처음 액세스할 때 이 작업이 수행됩니다. 시스템은 응용 프로그램이 개체를 처음으로 만들 때 단 한 번만 특정 개체에 대해 구성 파일을 조사합니다. 따라서 변경 내용을 적용하려면 응용 프로그램을 다시 시작해야 할 수 있습니다.  
  
 배포된 응용 프로그램에서는 응용 프로그램을 시작하기 전에 스위치 개체를 다시 구성하여 추적 코드를 사용하도록 설정합니다. 일반적으로 이 경우에는 스위치 개체를 설정 및 해제하거나 추적 수준을 변경한 다음 응용 프로그램을 다시 시작해야 합니다.  
  
## <a name="security-considerations"></a>보안 고려 사항  
 데이터를 로그에 쓸 때는 다음을 고려하세요.  
  
-   **사용자 정보가 누출되지 않도록 합니다.** 응용 프로그램에서 승인된 정보만 로그에 쓰도록 해야 합니다. 예를 들어 응용 프로그램 로그에 사용자 이름은 포함되어도 되지만 사용자 암호는 포함되지 않도록 하는 것이 좋습니다.  
  
-   **로그 위치의 보안을 강화합니다.** 잠재적으로 중요한 정보를 포함하는 모든 로그는 안전한 위치에 저장해야 합니다.  
  
-   **잘못된 정보를 사용하지 않도록 합니다.** 일반적으로 응용 프로그램에서는 사용자가 입력한 데이터를 사용하기 전에 이들 데이터의 유효성을 검증해야 합니다. 여기에는 응용 프로그램 로그에 데이터를 쓰는 작업도 포함됩니다.  
  
-   **서비스 거부가 발생하지 않도록 합니다.** 응용 프로그램에서 로그에 너무 많은 정보를 쓰면 로그가 가득 차거나 중요한 정보를 찾기가 어려워질 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 [응용 프로그램의 정보 기록](../../../../visual-basic/developing-apps/programming/log-info/index.md)
