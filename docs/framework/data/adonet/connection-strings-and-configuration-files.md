---
title: "연결 문자열 및 구성 파일"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 37df2641-661e-407a-a3fb-7bf9540f01e8
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 447b2d6c0e5eeafeaff89aa1d6430eec72d59a4d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="connection-strings-and-configuration-files"></a>연결 문자열 및 구성 파일
응용 프로그램 코드에 연결 문자열을 포함하면 보안상 취약한 부분이 생기고 유지 관리상의 문제가 발생할 수 있습니다. 사용 하 여 컴파일된 응용 프로그램의 소스 코드에는 암호화 되지 않은 연결 문자열을 볼 수는 [Ildasm.exe (IL 디스어셈블러)](../../../../docs/framework/tools/ildasm-exe-il-disassembler.md) 도구입니다. 뿐만 아니라 연결 문자열이 계속해서 변경되는 경우에는 응용 프로그램을 다시 컴파일해야 합니다. 이와 같은 여러 가지 이유로 연결 문자열은 응용 프로그램 구성 파일에 저장하는 것이 좋습니다.  
  
## <a name="working-with-application-configuration-files"></a>응용 프로그램 구성 파일 사용  
 응용 프로그램 구성 파일에는 특정 응용 프로그램과 관련된 설정이 들어 있습니다. ASP.NET 응용 프로그램을 하나 이상 포함할 수도 있습니다 예를 들어 **web.config** 파일 및 Windows 응용 프로그램 선택적 점이 **app.config** 파일입니다. 구성 파일의 이름과 위치는 응용 프로그램 호스트에 따라 다르지만 모든 구성 파일은 다음과 같은 공통 요소를 공유합니다.  
  
### <a name="the-connectionstrings-section"></a>connectionStrings 섹션  
 키/값 쌍으로 연결 문자열을 저장할 수 있습니다는 **connectionStrings** 의 섹션은 **구성** 응용 프로그램 구성 파일의 요소입니다. 자식 요소에는 **추가**, **지우기**, 및 **제거**합니다.  
  
 다음은 연결 문자열을 저장하기 위한 스키마 및 구문이 나와 있는 구성 파일의 일부분입니다. **이름** 특성은 고유 하 게 식별 연결 문자열을 런타임에 검색할 수 있도록 제공 하는 이름입니다. **providerName** machine.config 파일에 등록 되어 있는.NET Framework 데이터 공급자의 고정 이름입니다.  
  
```xml  
<?xml version='1.0' encoding='utf-8'?>  
  <configuration>  
    <connectionStrings>  
      <clear />  
      <add name="Name"   
       providerName="System.Data.ProviderName"   
       connectionString="Valid Connection String;" />  
    </connectionStrings>  
  </configuration>  
```  
  
> [!NOTE]
>  연결 문자열 일부를 구성 파일에 저장한 후 <xref:System.Data.Common.DbConnectionStringBuilder> 클래스를 사용하여 런타임에 연결 문자열을 완성할 수 있습니다. 이 기능은 사전에 연결 문자열 요소를 정확히 알고 있지 않거나 중요한 정보를 구성 파일에 저장하지 않으려는 경우에 유용합니다. 자세한 내용은 참조 [연결 문자열 작성기](../../../../docs/framework/data/adonet/connection-string-builders.md)합니다.  
  
### <a name="using-external-configuration-files"></a>외부 구성 파일 사용  
 외부 구성 파일은 단일 섹션으로 구성되며 구성 파일의 한 조각이 포함된 별도의 파일입니다. 외부 구성 파일은 기본 구성 파일에서 참조합니다. 저장 된 **connectionStrings** 실제로 별도 파일의 섹션은 응용 프로그램이 배포 된 후 연결 문자열이 편집 될 수 있는 경우에 유용 합니다. 예를 들어, 표준 ASP.NET 동작에서는 구성 파일이 수정되면 응용 프로그램 도메인을 다시 시작합니다. 따라서 상태 정보가 손실될 수 있습니다. 하지만 외부 구성 파일은 수정해도 응용 프로그램이 다시 시작되지 않습니다. 외부 구성 파일은 ASP.NET뿐만 아니라 Windows 응용 프로그램에도 사용될 수 있습니다. 파일 액세스 보안 및 권한을 사용하여 외부 구성 파일에 대한 액세스를 제한할 수도 있습니다. 런타임에 외부 구성 파일을 사용하는 것은 투명하게 수행되므로 특별한 코딩이 필요하지 않습니다.  
  
 외부 구성 파일에서 연결 문자열을 저장 하려면만 포함 하는 별도 파일을 만듭니다는 **connectionStrings** 섹션. 이외 다른 요소, 섹션 또는 특성은 포함하지 마세요. 다음 예제에서는 외부 구성 파일의 구문을 보여 줍니다.  
  
```xml  
<connectionStrings>  
  <add name="Name"   
   providerName="System.Data.ProviderName"   
   connectionString="Valid Connection String;" />  
</connectionStrings>  
```  
  
 기본 응용 프로그램 구성 파일을 사용 하 여는 **configSource** 특성을 정규화 된 이름 및 외부 파일의 위치를 지정 합니다. 다음 예제에서는 `connections.config`라는 외부 구성 파일을 참조합니다.  
  
```xml  
<?xml version='1.0' encoding='utf-8'?>  
<configuration>  
    <connectionStrings configSource="connections.config"/>  
</configuration>  
```  
  
## <a name="retrieving-connection-strings-at-run-time"></a>런타임에 연결 문자열 검색  
 .NET Framework 2.0에서는 런타임에 구성 파일에서 연결 문자열을 쉽게 검색할 수 있도록 <xref:System.Configuration> 네임스페이스에 새 클래스가 추가되었습니다. 이름 또는 공급자 이름을 사용하여 프로그래밍 방식으로 연결 문자열을 검색할 수 있습니다.  
  
> [!NOTE]
>  **machine.config** 파일에 포함 되어는 **connectionStrings** Visual Studio에서 사용 되는 연결 문자열을 포함 하는 섹션입니다. 공급자 이름으로 연결 문자열을 검색 하는 경우는 **app.config** Windows 응용 프로그램의 연결 문자열에서 파일 **machine.config** 에서로드된놓은다음항목을가져올**app.config**합니다. 추가 **지우기** 바로 뒤의 **connectionStrings** 로컬에정의된연결문자열만있도록요소를메모리에데이터구조에서상속된모든참조를제거**app.config** 파일 것으로 간주 됩니다.  
  
### <a name="working-with-the-configuration-classes"></a>구성 클래스 사용  
 .NET Framework 2.0부터는 로컬 컴퓨터의 구성 파일을 사용할 경우 더 이상 사용되지 않는 <xref:System.Configuration.ConfigurationManager> 대신 <xref:System.Configuration.ConfigurationSettings>가 사용됩니다. ASP.NET 구성 파일을 사용하는 경우에는 <xref:System.Web.Configuration.WebConfigurationManager>가 사용됩니다. 웹 서버에서 구성 파일을 사용 하도록 하 고와 같은 구성 파일 섹션에 프로그래밍 방식 액세스 허용 **system.web**합니다.  
  
> [!NOTE]
>  런타임에 구성 파일에 액세스하려면 호출자에게 권한을 부여해야 합니다. 필요한 권한은 응용 프로그램의 종류와 구성 파일 및 구성 파일의 위치에 따라 다릅니다. 자세한 내용은 참조 [구성 클래스를 사용 하 여](http://msdn.microsoft.com/library/98d2b386-baf6-4a17-974b-76e3b4c87acc) 및 <xref:System.Web.Configuration.WebConfigurationManager> ASP.NET 응용 프로그램 및 <xref:System.Configuration.ConfigurationManager> Windows 응용 프로그램에 대 한 합니다.  
  
 <xref:System.Configuration.ConnectionStringSettingsCollection>을 사용하여 응용 프로그램 구성 파일에서 연결 문자열을 검색할 수 있습니다. 컬렉션을 포함 <xref:System.Configuration.ConnectionStringSettings> 각각의 단일 항목을 나타내는 개체의 **connectionStrings** 섹션. 개체 속성은 연결 문자열 특성에 매핑되므로 이름 또는 공급자 이름을 지정하여 연결 문자열을 검색할 수 있습니다.  
  
|속성|설명|  
|--------------|-----------------|  
|<xref:System.Configuration.ConnectionStringSettings.Name%2A>|연결 문자열의 이름으로, 매핑되는 **이름** 특성입니다.|  
|<xref:System.Configuration.ConnectionStringSettings.ProviderName%2A>|정규화된 공급자 이름으로, 매핑되는 **providerName** 특성입니다.|  
|<xref:System.Configuration.ConnectionStringSettings.ConnectionString%2A>|연결 문자열입니다. 매핑되는 **connectionString** 특성입니다.|  
  
### <a name="example-listing-all-connection-strings"></a>예제: 모든 연결 문자열 나열  
 다음 예제에서는 `ConnectionStringSettings` 컬렉션을 반복한 후 <xref:System.Configuration.ConnectionStringSettings.Name%2A>, <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A> 및 <xref:System.Configuration.ConnectionStringSettings.ConnectionString%2A> 속성을 콘솔 창에 표시합니다.  
  
> [!NOTE]
>  일부 프로젝트 형식에는 System.Configuration.dll이 포함되어 있지 않으므로 구성 클래스를 사용하려면 먼저 System.Configuration.dll에 대한 참조를 설정해야 할 수도 있습니다. 특정 응용 프로그램 구성 파일의 이름과 위치는 응용 프로그램의 종류 및 호스팅 프로세스에 따라 달라집니다.  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfig#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfig/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfig#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfig/VB/source.vb#1)]  
  
### <a name="example-retrieving-a-connection-string-by-name"></a>예제: 이름을 사용하여 연결 문자열 검색  
 다음 예제에서는 이름을 지정하여 구성 파일에서 연결 문자열을 검색하는 방법을 보여 줍니다. 다음 코드에서는 <xref:System.Configuration.ConnectionStringSettings> 개체를 만들어 사용자가 제공한 입력 매개 변수가 <xref:System.Configuration.ConfigurationManager.ConnectionStrings%2A> 이름과 일치하는지 확인합니다. 일치하는 이름이 없으면 함수에서 `null`(Visual Basic의 경우 `Nothing`)을 반환합니다.  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByName#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByName/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByName#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByName/VB/source.vb#1)]  
  
### <a name="example-retrieving-a-connection-string-by-provider-name"></a>예제: 공급자 이름을 사용하여 연결 문자열 검색  
 형식에서 공급자 고정 이름을 지정 하 여 연결 문자열을 검색 하는 방법을 보여 주는이 예제 *System.Data.ProviderName*합니다. 코드에서 <xref:System.Configuration.ConnectionStringSettingsCollection>을 반복한 후 일치하는 첫 번째 <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A>에 대한 연결 문자열을 반환합니다. 공급자 이름이 없으면 이 함수가 `null`(Visual Basic의 경우 `Nothing`)을 반환합니다.  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/VB/source.vb#1)]  
  
## <a name="encrypting-configuration-file-sections-using-protected-configuration"></a>보호되는 구성을 사용하여 구성 파일 섹션 암호화  
 ASP.NET 2.0 라는 새로운 기능이 도입 *보호 되는 구성을*, 구성 파일의 중요 한 정보를 암호화할 수 있습니다. 보호되는 구성은 원래 ASP.NET용으로 디자인된 것이지만 Windows 응용 프로그램의 구성 파일 섹션을 암호화하는 데도 사용할 수 있습니다. 보호 되는 구성 기능에 대 한 자세한 내용은 참조 하세요. [암호화 구성 정보를 사용 하 여 보호 되는 구성](http://msdn.microsoft.com/library/51cdfe5b-9d82-458c-94ff-c551c4f38ed1)합니다.  
  
 다음 구성 파일 조각에서는 **connectionStrings** 후 암호화 된 섹션입니다. **configProtectionProvider** 암호화 하 고 연결 문자열을 해독 하는 데 사용 하는 보호 되는 구성 공급자를 지정 합니다. **EncryptedData** 섹션에는 암호화 텍스트가 들어 있습니다.  
  
```xml  
<connectionStrings configProtectionProvider="DataProtectionConfigurationProvider">  
  <EncryptedData>  
    <CipherData>  
      <CipherValue>AQAAANCMnd8BFdERjHoAwE/Cl+sBAAAAH2... </CipherValue>  
    </CipherData>  
  </EncryptedData>  
</connectionStrings>  
```  
  
 지정 된 공급자를 사용 하 여 암호를 해독 하는.NET Framework 암호화 된 연결 문자열에서 런타임에 검색 되는 **CipherValue** 응용 프로그램에 사용할 수 있도록 합니다. 따라서 암호를 해독하는 데 추가 코드를 작성할 필요가 없습니다.  
  
### <a name="protected-configuration-providers"></a>보호되는 구성 공급자  
 보호 되는 구성 공급자가 등록는 **configProtectedData** 의 섹션은 **machine.config** 두 보여 주는 다음 조각에서와 같이 로컬 컴퓨터에서의 파일 .NET Framework와 함께 제공 되는 보호 되는 구성 공급자입니다. 여기 표시된 값은 보기 편하도록 자른 것입니다.  
  
```xml  
<configProtectedData defaultProvider="RsaProtectedConfigurationProvider">  
  <providers>  
    <add name="RsaProtectedConfigurationProvider"   
      type="System.Configuration.RsaProtectedConfigurationProvider, ... />  
    <add name="DataProtectionConfigurationProvider"   
      type="System.Configuration.DpapiProtectedConfigurationProvider, ... />  
  </providers>  
</configProtectedData>  
```  
  
 에 추가 하 여 추가 보호 되는 구성 공급자를 구성할 수는 **machine.config** 파일입니다. <xref:System.Configuration.ProtectedConfigurationProvider> 추상 기본 클래스에서 상속하여 사용자 고유의 보호되는 구성 공급자를 만들 수도 있습니다. 다음 표에는 .NET Framework와 함께 포함된 두 개의 구성 파일이 설명되어 있습니다.  
  
|공급자|설명|  
|--------------|-----------------|  
|<!--zz<xref:System.Configuration.RSAProtectedConfigurationProvider>-->`System.Configuration.RSAProtectedConfigurationProvider`|RSA 암호화 알고리즘을 사용하여 데이터를 암호화하고 해독합니다. 공개 키 암호화 및 디지털 서명에도 RSA 알고리즘을 사용할 수 있습니다. 두 개의 서로 다른 키를 사용하므로 "공개 키" 또는 비대칭 암호화라고도 합니다. 사용할 수는 [ASP.NET IIS 등록 도구 (Aspnet_regiis.exe)](http://msdn.microsoft.com/library/6491c41e-e2b0-481f-9863-db3614d5f96b) Web.config 파일의 섹션을 암호화 하 여 암호화 키를 관리 합니다. ASP.NET에서는 파일을 처리할 때 구성 파일의 암호를 해독합니다. ASP.NET 응용 프로그램의 ID는 섹션을 암호화하고 해독하는 데 사용되는 암호화 키에 대해 읽기 액세스 권한이 있어야 합니다.|  
|<!--zz<xref:System.Configuration.DPAPIProtectedConfigurationProvider>-->`System.Configuration.DPAPIProtectedConfigurationProvider`|Windows DPAPI(데이터 보호 API)를 사용하여 구성 섹션을 암호화합니다. Windows 기본 제공 암호화 서비스를 사용하며 시스템별 또는 사용자 계정별로 보호되도록 구성할 수 있습니다. 시스템별 보호는 동일한 서버에 정보를 공유해야 하는 여러 응용 프로그램이 있을 때 유용합니다. 사용자 계정별 보호는 공유된 호스팅 환경과 같이 특정 사용자 ID와 함께 실행되는 서비스에서 사용할 수 있습니다. 각 응용 프로그램은 파일 및 데이터베이스와 같은 리소스에 대한 액세스를 제한하는 개별 ID에 대해 실행됩니다.|  
  
 두 공급자 모두 강력한 데이터 암호화를 제공합니다. 그러나 웹 팜과 같이 여러 서버에서 동일한 암호화 구성 파일을 사용하려는 경우 데이터를 암호화하는 데 사용되는 암호화 키를 내보내고 다른 서버에서 가져오도록 하려면 `RsaProtectedConfigurationProvider`를 사용해야 합니다. 자세한 내용은 참조 [가져오기 및 내보내기 보호 구성 RSA 키 컨테이너](http://msdn.microsoft.com/library/f3022b39-f17f-48c1-b067-025eab0ce8bc)합니다.  
  
### <a name="using-the-configuration-classes"></a>구성 클래스 사용  
 <xref:System.Configuration> 네임스페이스에서는 프로그래밍 방식으로 구성을 설정하는 클래스를 제공합니다. <xref:System.Configuration.ConfigurationManager> 클래스에서는 시스템, 응용 프로그램 및 사용자 구성 파일에 대한 액세스를 제공합니다. ASP.NET 응용 프로그램을 만드는 경우 사용할 수 있습니다는 <xref:System.Web.Configuration.WebConfigurationManager> 클래스에 있는 같은 ASP.NET 응용 프로그램에 고유한 설정에 액세스할 수 있도록 하는 동안 동일한 기능을 제공 하는  **\< system.web >**합니다.  
  
> [!NOTE]
>  <xref:System.Security.Cryptography> 네임스페이스에는 데이터를 암호화하고 해독하는 추가 옵션을 제공하는 클래스가 들어 있습니다. 보호되는 구성을 사용하여 처리할 수 없는 암호화 서비스가 필요한 경우 이러한 클래스를 사용합니다. 이러한 클래스 중 일부는 관리되지 않는 Microsoft CryptoAPI에 대한 래퍼이지만 나머지는 완전하게 관리되는 구현 클래스입니다. 자세한 내용은 [암호화 서비스](http://msdn.microsoft.com/library/68a1e844-c63c-44af-9247-f6716eb23781)를 참조하세요.  
  
### <a name="appconfig-example"></a>App.config 예제  
 이 예제에서는 암호화를 전환 하는 **connectionStrings** 섹션는 **app.config** Windows 응용 프로그램에 대 한 파일입니다. 이 예제의 프로시저에서는 응용 프로그램 이름을 인수로 사용합니다(예: "MyApplication.exe"). **app.config** 파일 암호화 한 다음 이름이 "myapplication.exe.config"인 실행 파일이 포함 된 폴더에 복사 합니다.  
  
> [!NOTE]
>  연결 문자열은 암호화된 컴퓨터에서만 해독될 수 있습니다.  
  
 코드를 사용 하 여는 <xref:System.Configuration.ConfigurationManager.OpenExeConfiguration%2A> 열려는 메서드는 **app.config** 편집할 파일을 및 <xref:System.Configuration.ConfigurationManager.GetSection%2A> 메서드가 반환 되는 **connectionStrings** 섹션. 그런 다음 코드에서 <xref:System.Configuration.SectionInformation.IsProtected%2A> 속성을 확인하여 섹션이 암호화되지 않은 경우 섹션을 암호화하는 <xref:System.Configuration.SectionInformation.ProtectSection%2A>을 호출합니다. 섹션의 암호를 해독하려면 <xref:System.Configuration.SectionInformation.UnprotectSection%2A> 메서드를 호출합니다. <xref:System.Configuration.Configuration.Save%2A> 메서드가 작업을 완료하고 변경 내용을 저장합니다.  
  
> [!NOTE]
>  코드를 실행하려면 프로젝트에서 `System.Configuration.dll`에 대한 참조를 설정해야 합니다.  
  
 [!code-csharp[DataWorks ConnectionStrings.Encrypt#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStrings.Encrypt/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStrings.Encrypt#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStrings.Encrypt/VB/source.vb#1)]  
  
### <a name="webconfig-example"></a>Web.config 예제  
 이 예제에서는 <xref:System.Web.Configuration.WebConfigurationManager.OpenWebConfiguration%2A>의 `WebConfigurationManager` 메서드를 사용합니다. 이 경우에 제공할 수 있습니다에 상대 경로 **Web.config** 물결표를 사용 하 여 파일입니다. 코드에는 `System.Web.Configuration` 클래스에 대한 참조가 있어야 합니다.  
  
 [!code-csharp[DataWorks ConnectionStringsWeb.Encrypt#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringsWeb.Encrypt/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringsWeb.Encrypt#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringsWeb.Encrypt/VB/source.vb#1)]  
  
 자세한 내용은 ASP.NET 응용 프로그램 보안에 대 한 참조 [NIB: ASP.NET 보안](http://msdn.microsoft.com/library/04b37532-18d9-40b4-8e5f-ee09a70b311d) 및 [를 한 눈에 ASP.NET 2.0 보안 사례](http://go.microsoft.com/fwlink/?LinkId=59997) ASP.NET 개발자 센터에서.  
  
## <a name="see-also"></a>참고 항목  
 [연결 문자열 작성기](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 [구성 클래스를 사용 하 여](http://msdn.microsoft.com/library/98d2b386-baf6-4a17-974b-76e3b4c87acc)  
 [응용 프로그램 구성](../../../../docs/framework/configure-apps/index.md)  
 [ASP.NET 웹 사이트 관리](http://msdn.microsoft.com/library/1298034b-5f7d-464d-abd1-ad9e6b3eeb7e)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
