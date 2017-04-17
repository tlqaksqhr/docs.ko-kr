---
title: ".NET Framework의 새로운 기능 | Microsoft Docs"
ms.custom: ""
ms.date: "04/07/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "새로운 기능[.NET Framework]"
ms.assetid: 1d971dd7-10fc-4692-8dac-30ca308fc0fa
caps.latest.revision: 292
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 287
---
# .NET Framework의 새로운 기능
<a name="introduction"></a>이 문서는 새로운 주요 기능 및 다음 버전의.NET Framework의 향상 된 기능을 요약합니다.  
  
 [.NET framework 4.6.2](#v462)   
 [.NET framework 4.6.1](#v461)   
 [.NET 2015 및.NET Framework 4.6](#v46)   
 [.NET framework 4.5.2](#v452)   
 [.NET framework 4.5.1](#v451)   
 [.NET framework 4.5](#core)  
  
 이 문서는 각 새로운 기능에 대한 포괄적인 정보를 제공하지 않으며 변경될 수 있습니다. .NET Framework에 대 한 일반 정보를 참조 하십시오. [시작](../../../docs/framework/get-started/index.md)합니다. 지원 되는 플랫폼에 대 한 참조 [시스템 요구 사항](../../../docs/framework/get-started/system-requirements.md)합니다. 다운로드 링크 및 설치 지침을 참조 하십시오. [설치 가이드](../../../docs/framework/install/guide-for-developers.md)합니다.  
  
> [!NOTE]
>  또한.NET Framework 팀에서 플랫폼 지원을 확장 하 고 변경할 수 없는 컬렉션 및 SIMD 사용 벡터 형식 등의 새로운 기능을 소개 하는 NuGet이 포함 된 대역 외에서 기능을 해제 합니다. 자세한 내용은 참조 [추가 클래스 라이브러리 및 Api](../../../ml/index.xml) 및 [.NET Framework 및 번 외 릴리스](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)합니다. 참조는 [NuGet 패키지의 전체 목록은](http://blogs.msdn.com/b/dotnet/p/nugetpackages.aspx) .NET Framework에 대 한 구독 또는 [우리의 피드](https://nuget.org/api/v2/curated-feeds/dotnetframework/Packages/)합니다.  
  
<a name="v462"></a>   
## <a name="introducing-the-net-framework-462"></a>.NET Framework 4.6.2 소개  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]는 .NET Framework 4.6 및 4.6.1에서 빌드되며 제품의 안정성을 유지하면서 많은 새로운 수정 및 여러 가지 새 기능이 추가됩니다.  
  
### <a name="downloading-and-installing-the-net-framework-462"></a>.NET Framework 4.6.2 다운로드 및 설치  
 다음 위치에서 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 다운로드할 수 있습니다.  
  
-   [.NET framework 4.6.2 웹 설치 관리자](http://go.microsoft.com/fwlink/?LinkId=780597)  
  
-   [NET Framework 4.6.2 오프 라인 설치 관리자](http://go.microsoft.com/fwlink/?LinkId=780601)  
  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]는 Windows 10, Windows 8.1, Windows 7 및 Windows Server 2008 R2 SP1 이상의 해당 서버 플랫폼에 설치할 수 있습니다. 웹 설치 관리자 또는 오프라인 설치 관리자를 사용하여 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 설치할 수 있습니다. 대부분의 사용자에게 권장되는 방법은 웹 설치 관리자를 사용하는 것입니다.  
  
 대상으로 지정할 수 있습니다는 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] Visual Studio 2012에서 또는 설치 하 여 나중에 [4.6.2.NET Framework 개발자 팩](http://go.microsoft.com/fwlink/?LinkId=780617)합니다.  
  
### <a name="whats-new-in-the-net-framework-462"></a>.NET Framework 4.6.2의 새로운 기능  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]에는 다음과 같은 영역의 새 기능이 포함됩니다.  
  
-   [ASP.NET](#ASPNET462)  
  
-   [문자 범주](#Strings)  
  
-   [암호화](#Crypto462)  
  
-   [SqlClient](#SQLClient)  
  
-   [Windows Communication Foundation](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF462)  
  
-   [Windows Workflow Foundation (WF)](#WF462)  
  
-   [ClickOnce](#ClickOnce)  
  
-   [UWP 앱을 Windows Forms 및 WPF 응용 프로그램 변환](#UWPConvert)  
  
-   [디버깅 기능 향상](#Debug462)  
  
 새로운 Api의 목록에 추가 된 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], 참조 [4.6.2.NET Framework API 변경 내용](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-api-changes.md) GitHub에서. 향상 된 기능 및 버그 수정 사항이 목록은 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], 참조 [4.6.2.NET Framework API 변경 내용](http://go.microsoft.com/fwlink/?LinkId=708778) GitHub에서.  자세한 내용은 참조 [.NET Framework 발표 4.6.2](https://blogs.msdn.microsoft.com/dotnet/2016/08/02/announcing-net-framework-4-6-2/) .NET 블로그의 합니다.  
  
<a name="ASPNET462"></a>   
### <a name="aspnet"></a>ASP.NET  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]의 ASP.NET에는 다음과 같은 향상된 기능이 포함되어 있습니다.  
  
 **데이터 주석 유효성 검사기의 지역화 된 오류 메시지에 대 한 향상 된 지원**  
 데이터 주석 유효성 검사기를 통해 클래스 속성에 하나 이상의 특성을 추가하여 유효성 검사를 수행할 수 있습니다. 특성의 <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=fullName> 요소 유효성 검사가 실패 하면 오류 메시지의 텍스트를 정의 합니다. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 이상에서는 ASP.NET을 사용하여 오류 메시지를 쉽게 지역화할 수 있습니다. 다음과 같은 경우에 오류 메시지를 지역화합니다.  
  
1.  <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=fullName> 유효성 검사 특성에 제공 됩니다.  
  
2.  리소스 파일 App_LocalResources 폴더에 저장되어 있는 경우  
  
3.  지역화 된 리소스 파일의 이름은 `DataAnnotation.Localization.{` *이름*`}.resx`여기서 *이름* 형식의 문화권 이름 *languageCode*`-`*국가/지역 번호* 또는 *languageCode*합니다.  
  
4.  리소스의 키 이름은에 할당 된 문자열은 <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=fullName> 특성과 해당 값은 지역화 된 오류 메시지입니다.  
  
 예를 들어, 다음 데이터 주석 특성은 잘못 된 등급에 대 한 기본 문화권의 오류 메시지를 정의합니다.  
  
```csharp  
  
public class RatingInfo  
{  
   [Required(ErrorMessage = "The rating must be between 1 and 10.")]  
   [Display(Name = "Your Rating")]  
   public int Rating { get; set; }  
}  
  
```  
  
```vb  
  
Public Class RatingInfo  
   <Required(ErrorMessage = "The rating must be between 1 and 10.")>  
   <Display(Name = "Your Rating")>  
   Public Property Rating As Integer = 1  
End Class  
  
```  
  
 그런 다음 DataAnnotation.Localization.fr.resx, 오류 메시지 문자열 키는 하며 해당 값이 지역화 된 오류 메시지 리소스 파일을 만들 수 있습니다. 파일에서 발견 되어야는 `App.LocalResources` 폴더입니다. 예를 들어 다음은 프랑스어 (fr) 언어는 지역화 된 오류 메시지에 해당 값과 키입니다.  
  
|이름|값|  
|----------|-----------|  
|이 등급은 1에서 10 사이 여야 합니다.|Doit ê entre 1을 구성 하는 la 참고 et 10입니다.|  
  
 그런 다음이 파일  
  
 또한, 데이터 주석 지역화를 확장할 수 있습니다. 개발자가 구현 하 여 고유한 문자열 지역화 담당자가 공급자에 연결할 수는 <xref:System.Web.Globalization.IStringLocalizerProvider> 지역화에 문자열을 저장할 위치 이외의 다른 리소스 파일에 대 한 인터페이스입니다.  
  
 **세션 상태 저장소 공급자와 비동기 지원**  
 이제 ASP.NET을 통해 태스크 반환 메서드를 세션 상태 저장소 공급자와 함께 사용할 수 있으므로, ASP.NET 앱에서 비동기화의 확장성 이점을 누릴 수 있습니다. 저장소 공급자를 세션 상태와 비동기 작업을 지원, 새로운 인터페이스를 포함 하는 ASP.NET <xref:System.Web.SessionState.ISessionStateModule?displayProperty=fullName>에서 상속한 <xref:System.Web.IHttpModule> 개발자는 자신의 세션 상태 모듈과 비동기 세션 저장소 공급자를 구현할 수 있습니다. 인터페이스는 다음과 같이 정의됩니다.  
  
```csharp  
  
public interface ISessionStateModule : IHttpModule {  
    void ReleaseSessionState(HttpContext context);  
    Task ReleaseSessionStateAsync(HttpContext context);  
}  
  
```  
  
 또한는 <xref:System.Web.SessionState.SessionStateUtility> 클래스는 두 개의 새로운 메서드를 포함 <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateReadOnly%2A> 및 <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateRequired%2A>, 비동기 작업을 지원 하기 위해 사용할 수 있습니다.  
  
 **출력 캐시 공급자에 대 한 비동기 지원**  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 이상에서는 태스크 반환 메서드를 출력 캐시 공급자와 함께 사용하여 비동기화의 확장성 이점을 제공할 수 있습니다.  이러한 메서드를 구현하는 공급자는 웹 서버에서 스레드 차단을 줄이고 ASP.NET 서비스의 확장성을 개선합니다.  
  
 비동기 출력 캐시 공급자를 지원하기 위해 다음 API를 추가했습니다.  
  
-   <xref:System.Web.Caching.OutputCacheProviderAsync?displayProperty=fullName> 클래스에서 상속 되는 <xref:System.Web.Caching.OutputCacheProvider?displayProperty=fullName> 개발자는 비동기 출력 캐시 공급자를 구현할 수 있습니다.  
  
-   <xref:System.Web.Caching.OutputCacheUtility> 출력 캐시를 구성 하기 위한 도우미 메서드를 제공 하는 클래스입니다.  
  
-   18 새 메서드는 <xref:System.Web.HttpCachePolicy?displayProperty=fullName>클래스입니다. 여기에 포함 <xref:System.Web.HttpCachePolicy.GetCacheability%2A>, <xref:System.Web.HttpCachePolicy.GetCacheExtensions%2A>, <xref:System.Web.HttpCachePolicy.GetETag%2A>, <xref:System.Web.HttpCachePolicy.GetETagFromFileDependencies%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetNoStore%2A>, <xref:System.Web.HttpCachePolicy.GetNoTransforms%2A>, <xref:System.Web.HttpCachePolicy.GetOmitVaryStar%2A>, <xref:System.Web.HttpCachePolicy.GetProxyMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetRevalidation%2A>, <xref:System.Web.HttpCachePolicy.GetUtcLastModified%2A>, <xref:System.Web.HttpCachePolicy.GetVaryByCustom%2A>, <xref:System.Web.HttpCachePolicy.HasSlidingExpiration%2A>, 및 <xref:System.Web.HttpCachePolicy.IsValidUntilExpires%2A>합니다.  
  
-   2 새 메서드는 <xref:System.Web.HttpCacheVaryByContentEncodings?displayProperty=fullName> 클래스: <xref:System.Web.HttpCacheVaryByContentEncodings.GetContentEncodings%2A> 및 <xref:System.Web.HttpCacheVaryByContentEncodings.SetContentEncodings%2A>합니다.  
  
-   2 새 메서드는 <xref:System.Web.HttpCacheVaryByHeaders?displayProperty=fullName> 클래스: <xref:System.Web.HttpCacheVaryByHeaders.GetHeaders%2A> 및 <xref:System.Web.HttpCacheVaryByHeaders.SetHeaders%2A>합니다.  
  
-   2 새 메서드는 <xref:System.Web.HttpCacheVaryByParams?displayProperty=fullName> 클래스: <xref:System.Web.HttpCacheVaryByParams.GetParams%2A> 및 <xref:System.Web.HttpCacheVaryByParams.SetParams%2A>합니다.  
  
-   에 <xref:System.Web.Caching.AggregateCacheDependency?displayProperty=fullName> 클래스는 <xref:System.Web.Caching.AggregateCacheDependency.GetFileDependencies%2A> 메서드.  
  
-   에 <xref:System.Web.Caching.CacheDependency>, <xref:System.Web.Caching.CacheDependency.GetFileDependencies%2A> 메서드.  
  
<a name="Strings"></a>   
### <a name="character-categories"></a>문자 범주  
 문자는 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 에 따라 분류 됩니다는 [유니코드 표준, 버전 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/)합니다. [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 및 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]의 문자는 유니코드 6.3 문자 범주를 기반으로 분류됩니다.  
  
 유니코드 8.0에 대 한 지원은 제한 문자 분류에는 <xref:System.Globalization.CharUnicodeInfo> 클래스와 형식 및 메서드를 사용 하는 것입니다. 여기에 <xref:System.Globalization.StringInfo> 클래스를 오버 로드 된 <xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName> 메서드를 및 [문자 클래스](../../../docs/standard/base-types/character-classes-in-regular-expressions.md) .NET Framework 정규식 엔진에서 인식 합니다.  문자 및 문자열 비교와 정렬은 이 변경의 영향을 받지 않으며, 기본 운영 체제, Windows 7 시스템 또는 .NET Framework에서 제공하는 문자 데이터를 계속해서 사용합니다.  
  
 유니코드 7.0 유니코드 6.0에서 문자 범주에 변경 내용에 대 한 참조 [유니코드 표준을, 버전 7.0.0까지 차단](http://www.unicode.org/versions/Unicode7.0.0/) 유니코드 컨소시엄 웹 사이트입니다. 유니코드 7.0에서 유니코드 8.0에 변경에 대 한 참조 [유니코드 표준을, 버전 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/) 유니코드 컨소시엄 웹 사이트입니다.  
  
<a name="Crypto462"></a>   
### <a name="cryptography"></a>암호화  
 **X509에 대 한 지원이 포함 된 FIPS 186 3 DSA 인증서**  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]에서는 키가 FIPS 186-2 1024비트 제한을 초과하는 DSA(디지털 서명 알고리즘) X509 인증서에 대한 지원을 추가했습니다.  
  
 FIPS 186-3의 더 큰 키 크기를 지원할 뿐만 아니라 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]에서는 SHA-2 해시 알고리즘 패밀리(SHA256, SHA384 및 SHA512)를 통한 컴퓨팅 시그니처를 허용합니다. FIPS 186 3에서 지원을 제공 새 <xref:System.Security.Cryptography.DSACng?displayProperty=fullName> 클래스입니다.  
  
 최신 변경 내용에 따라는 <xref:System.Security.Cryptography.RSA> .NET Framework 4.6의 클래스 및 <xref:System.Security.Cryptography.ECDsa> 4.6.1,.NET Framework의 클래스는 <xref:System.Security.Cryptography.DSA> 추상 기본 클래스에서 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 추가 하는 방법이 있습니다 캐스팅 하지 않고이 기능을 사용 하 여 호출자를 허용 합니다. 호출할 수는 <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A?displayProperty=fullName> 확장 메서드를 다음 예제와 같이 데이터에 서명 합니다.  
  
```csharp  
  
public static byte[] SignDataDsaSha384(byte[] data, X509Certificate2 cert)  
{  
    using (DSA dsa = cert.GetDSAPrivateKey())  
    {  
        return dsa.SignData(data, HashAlgorithmName.SHA384);  
    }  
}  
  
```  
  
```vb  
  
Public Shared Function SignDataDsaSha384(data As Byte(), cert As X509Certificate2) As Byte()  
    Using DSA As DSA = cert.GetDSAPrivateKey()  
        Return DSA.SignData(data, HashAlgorithmName.SHA384)  
    End Using  
End Function  
  
```  
  
 호출할 수는 <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A?displayProperty=fullName> 확장 메서드를 다음 예제와 같이 서명 된 데이터를 확인 합니다.  
  
```csharp  
  
public static bool VerifyDataDsaSha384(byte[] data, byte[] signature, X509Certificate2 cert)  
{  
    using (DSA dsa = cert.GetDSAPublicKey())  
    {  
        return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384);  
    }  
}  
  
```  
  
```  
  
 Public Shared Function VerifyDataDsaSha384(data As Byte(), signature As Byte(), cert As X509Certificate2) As Boolean  
    Using dsa As DSA = cert.GetDSAPublicKey()  
        Return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384)  
    End Using  
End Function  
  
```  
  
 **ECDiffieHellman 키 파생 루틴에 대 한 입력에 대 한 향상 된 명확성**  
 .NET Framework 3.5에서는 세 가지 KDF(키 파생 함수) 루틴을 가진 타원 곡선 Diffie-Hellman 키 계약에 대한 지원을 추가했습니다. 루틴 및 자체 루틴에 대 한 입력 속성을 통해 구성 된는 <xref:System.Security.Cryptography.ECDiffieHellmanCng> 개체입니다. 하지만 일부 루틴이 일부 입력 속성을 읽지 않기 때문에 개발자의 과거에 대해 혼동을 일으킬 여지가 충분합니다.  
  
 이 문제를 해결 하는 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를에 추가 된 다음 세 가지 방법의 <xref:System.Security.Cryptography.ECDiffieHellman> 기본 클래스를 보다 명확 하 게 이러한 KDF 루틴 및 해당 입력을 나타내는:  
  
|ECDiffieHellman 메서드|설명|  
|----------------------------|-----------------|  
|[DeriveKeyFromHash (ECDiffieHellmanPublicKey, HashAlgorithmName, 바이트\[\], 바이트\<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHash%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|수식을 사용하여 키 자료 파생<br /><br /> HASH(secretPrepend || *x* | | secretAppend)<br /><br /> 해시 (secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> 여기서 *x* EC Diffie-hellman 알고리즘의 계산된 결과입니다.|  
|[DeriveKeyFromHmac (ECDiffieHellmanPublicKey, HashAlgorithmName, 바이트\[\], 바이트\[\], 바이트\<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHmac%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|수식을 사용하여 키 자료 파생<br /><br /> HMAC (hmacKey, secretPrepend | | *x* | | secretAppend)<br /><br /> HMAC (hmacKey, secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> 여기서 *x* EC Diffie-hellman 알고리즘의 계산된 결과입니다.|  
|[DeriveKeyTls (ECDiffieHellmanPublicKey, 바이트\[\], 바이트\<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyTls%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|TLS PRF(의사 난수 함수) 파생 알고리즘을 사용하여 키 자료 파생|  
  
 **지속형 키가 대칭 암호화에 대 한 지원**  
 Windows 암호화 라이브러리(CNG)에서는 지속형 대칭 키 저장과 하드웨어에 저장된 대칭 키 사용에 대한 지원을 추가했습니다. 개발자는 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 통해 이 기능을 활용할 수 있습니다.  키 이름과 키 공급자가 구현별로 다르게 표시되므로, 이 기능을 사용하려면 기본 팩토리 접근 방식 대신 구체적인 구현 형식의 생성자를 활용해야 합니다(예: `Aes.Create` 호출).  
  
 대칭 암호화 키 유지 지원은 aes (<xref:System.Security.Cryptography.AesCng>) 및 3DES (<xref:System.Security.Cryptography.TripleDESCng>) 알고리즘입니다. 예를 들면 다음과 같습니다.  
  
```csharp  
  
public static byte[] EncryptDataWithPersistedKey(byte[] data, byte[] iv)  
{  
    using (Aes aes = new AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider))  
    {  
        aes.IV = iv;  
  
        // Using the zero-argument overload is required to make use of the persisted key  
        using (ICryptoTransform encryptor = aes.CreateEncryptor())  
        {  
            if (!encryptor.CanTransformMultipleBlocks)  
            {  
                throw new InvalidOperationException("This is a sample, this case wasn’t handled...");  
            }  
  
            return encryptor.TransformFinalBlock(data, 0, data.Length);  
        }  
    }  
}  
  
```  
  
```vb  
  
Public Shared Function EncryptDataWithPersistedKey(data As Byte(), iv As Byte()) As Byte()  
    Using Aes As Aes = New AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider)  
        Aes.IV = iv  
  
        ' Using the zero-argument overload Is required to make use of the persisted key  
        Using encryptor As ICryptoTransform = Aes.CreateEncryptor()  
            If Not encryptor.CanTransformMultipleBlocks Then  
                Throw New InvalidOperationException("This is a sample, this case wasn’t handled...")  
            End If  
            Return encryptor.TransformFinalBlock(data, 0, data.Length)  
        End Using  
    End Using  
End Function  
  
```  
  
 **Sha-2 해시 SignedXml 지원**  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 지원을 추가 하는 <xref:System.Security.Cryptography.Xml.SignedXml> rsa-sha256, RSA SHA384, SHA512 RSA PKCS&#1; 서명 방법, 및 SHA256, SHA384, SHA512 참조에 대 한 다이제스트 알고리즘 클래스입니다.  
  
 URI 상수에서 노출 된 모든 <xref:System.Security.Cryptography.Xml.SignedXml>:  
  
|SignedXml 필드|상수|  
|---------------------|--------------|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA256Url>|"http://www.w3.org/2001/04/xmlenc#sha256"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA256Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#sha384"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha384"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA512Url>|"http://www.w3.org/2001/04/xmlenc#sha512"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA512Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha512"|  
  
 사용자 지정을 등록 한 모든 프로그램 <xref:System.Security.Cryptography.SignatureDescription> 처리기에 <xref:System.Security.Cryptography.CryptoConfig> 이러한 알고리즘은 계속 이전에 로드가 표시 되므로 이제 플랫폼의 기본 작동에 대 한 지원을 추가 하는 <xref:System.Security.Cryptography.CryptoConfig> 등록은 필요 하지 않습니다.  
  
<a name="SQLClient"></a>   
### <a name="sqlclient"></a>SqlClient  
 .NET framework Data Provider for SQL Server (<xref:System.Data.SqlClient?displayProperty=fullName>)는 다음과 같은 새 기능에 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]:  
  
 **연결 풀링 및 Azure SQL 데이터베이스 제한 시간**  
 연결 풀링을 사용하도록 설정한 상태에서 시간 초과 또는 다른 오류가 발생할 경우 예외가 캐시되고 다음에 연결하려고 시도할 때 캐시된 예외가 5초-1분 동안 throw됩니다.  자세한 내용은 다음을 참조 하십시오. [SQL Server 연결 풀링 (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md)합니다.  
  
 Azure SQL Database에 연결할 때 일반적으로 빠르게 복구되는 일시적인 오류로 인해 연결 시도가 실패할 수 있으므로 이 동작은 바람직하지 않습니다. 연결 재시도 경험을 효율적으로 최적화하기 위해 Azure SQL Database 연결이 실패할 때 연결 풀 차단 기간 동작을 제거합니다.  
  
 새로운 `PoolBlockingPeriod` 키워드를 추가하여 앱에 가장 적합한 차단 기간을 선택할 수 있습니다. 값은 다음과 같습니다.  
  
 `Auto`  
 Azure SQL Database에 연결하는 응용 프로그램에 대한 연결 풀 차단 기간은 비활성화되고, 다른 SQL Server 인스턴스에 연결하는 응용 프로그램에 대한 연결 풀 차단 기간은 활성화됩니다. 기본값입니다. 서버 끝점 이름이 다음 중 하나로 끝나는 경우 Azure SQL Database로 간주됩니다.  
  
-   .database.windows.net  
  
-   .database.chinacloudapi.cn  
  
-   .database.usgovcloudapi.net  
  
-   .database.cloudapi.de  
  
 `AlwaysBlock`  
 연결 풀 차단 기간이 항상 활성화됩니다.  
  
 `NeverBlock`  
 연결 풀 차단 기간이 항상 비활성화됩니다.  
  
 **향상 된 기능 항상 암호화에 대 한**  
 SQLClient에서는 상시 암호화에 대한 두 가지 향상된 기능을 도입했습니다.  
  
-   암호화된 데이터베이스 열에 대한 매개 변수화된 쿼리 성능을 향상하기 위해 이제 쿼리 매개 변수에 대한 암호화 메타데이터가 캐시됩니다. 와 <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled%2A?displayProperty=fullName> 속성으로 설정 `true` (기본값) 인 동일한 쿼리를 여러 번 호출 되 면 클라이언트 매개 변수 메타 데이터는 서버에서 한 번만 검색 합니다.  
  
-   열 암호화 키 항목 키 캐시에 사용 하 여 설정 하는 구성 가능한 시간 제한 간격 후 제거 되는 이제는 <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionKeyCacheTtl%2A?displayProperty=fullName> 속성입니다.  
  
<a name="WCF"></a>   
### <a name="windows-communication-foundation"></a>Windows Communication Foundation  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]에서 Windows Communication Foundation이 다음과 같은 영역에서 향상되었습니다.  
  
 **CNG를 사용 하 여 저장 하는 인증서에 대 한 WCF 전송 보안 지원**  
 WCF 전송 보안에서 Windows 암호화 라이브러리(CNG)를 사용하여 저장한 인증서를 지원합니다. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]에서 이 지원은 지수 길이가 32비트 이하인 공개 키로 인증서를 사용하도록 제한됩니다. 응용 프로그램이 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 경우 이 기능은 기본적으로 켜집니다.  
  
 대상으로 하는 응용 프로그램에 대 한는 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 하지만 이전 버전에서 실행 되 고는 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], 다음 줄을 추가 하 여이 기능을 활성화 하려면는 [ <> \> ](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) app.config 또는 web.config 파일의 섹션입니다.  
  
```xml  
  
<AppContextSwitchOverrides  
    value="Switch.System.ServiceModel.DisableCngCertificates=false"  
/>  
  
```  
  
 다음과 같은 코드를 사용하여 프로그래밍 방식으로 이 작업을 수행할 수도 있습니다.  
  
```csharp  
  
private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificates";  
AppContext.SetSwitch(disableCngCertificates, false);  
  
```  
  
```vb  
  
Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates"  
AppContext.SetSwitch(disableCngCertificates, False)  
  
```  
  
 **DataContractJsonSerializer 클래스에 의해 여러 일광 절약 시간 조정 규칙에 대 한 지원 향상**  
 고객이 확인 하는 응용 프로그램 구성 설정을 사용할 수 있는지 여부를 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 클래스는 단일 표준 시간대에 대 한 여러 조정 규칙을 지원 합니다. 이 기능은 옵트인(opt-in) 기능입니다. 이 기능을 사용하려면 app.config 파일에 다음 설정을 추가합니다.  
  
```xml  
  
<runtime>  
     <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseTimeZoneInfo=false" />  
</runtime>  
  
```  
  
 이 기능을 사용 하는 경우는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 개체에서 사용 하는 <xref:System.TimeZoneInfo> 형식 대신는 <xref:System.TimeZone> 날짜 및 시간 데이터를 deserialize 할 형식입니다. <xref:System.TimeZoneInfo> ; 시간대 기록 데이터를 사용할 수 있는 여러 개의 조정 규칙을 지원   <xref:System.TimeZone> 하지 않습니다.  
  
 대 한 자세한 내용은 <xref:System.TimeZoneInfo> 구조 및 참조 되는 표준 시간대 조정 [표준 시간대 개요](../../../docs/standard/datetime/time-zone-overview.md)합니다.  
  
 **UTC를 유지 하는 것에 대 한 지원 시간 직렬화 및 역직렬화 XMLSerializer 클래스**  
 일반적으로,는 <xref:System.Xml.Serialization.XmlSerializer> 클래스는 UTC를 serialize 하는 데 사용 됩니다 <xref:System.DateTime> 값, 날짜 및 시간을 유지 하지만 로컬 시간을 가정 하는 직렬화 된 시간 문자열을 만듭니다.  예를 들어 다음 코드를 호출하여 UTC 날짜 및 시간을 인스턴스화하는 경우  
  
```csharp  
DateTime utc = new DateTime(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc);  
```  
  
```vb  
Dim utc As New Date(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc)  
```  
  
 UTC보다&8;시간 늦은 시스템에 대해 serialize된 시간 문자열 "03:00:00.0000000-08:00"이 결과로 제공됩니다.  serialize된 값은 항상 로컬 날짜 및 시간 값으로 deserialize됩니다.  
  
 응용 프로그램 구성 설정을 사용 하 여 확인 하 여부는 <xref:System.Xml.Serialization.XmlSerializer> UTC 표준 시간대 정보를 직렬화 할 때 및 역직렬화 하는 동안 유지 <xref:System.DateTime> 값:  
  
```xml  
  
<runtime>  
     <AppContextSwitchOverrides   
          value="Switch.System.Runtime.Serialization.DisableSerializeUTCDateTimeToTimeAndDeserializeUTCTimeToUTCDateTime=false" />  
</runtime>  
  
```  
  
 이 기능을 사용 하는 경우는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 개체에서 사용 하는 <xref:System.TimeZoneInfo> 형식 대신는 <xref:System.TimeZone> 날짜 및 시간 데이터를 deserialize 할 형식입니다. <xref:System.TimeZoneInfo> ; 시간대 기록 데이터를 사용할 수 있는 여러 개의 조정 규칙을 지원   <xref:System.TimeZone> 하지 않습니다.  
  
 대 한 자세한 내용은 <xref:System.TimeZoneInfo> 구조 및 참조 되는 표준 시간대 조정 [표준 시간대 개요](../../../docs/standard/datetime/time-zone-overview.md)합니다.  
  
 **NetNamedPipeBinding 가장 일치 하는**  
 WCF에는 클라이언트 응용 프로그램에서 요청한 항목과 가장 일치하는 URI를 수신하는 서비스에 항상 연결하도록 설정 가능한 새 앱 설정이 있습니다. 로 설정 하는이 응용 프로그램 설정으로 `false` 가 사용 하는 클라이언트 수 (기본값) 이면 <xref:System.ServiceModel.NetNamedPipeBinding> 요청된 된 URI의 부분 문자열 하는 URI에서 수신 대기 하는 서비스에 연결 하려고 합니다.  
  
 예를 들어 클라이언트가 `net.pipe://localhost/Service1`에서 수신하는 서비스에 연결하려고 하지만, 관리자 권한으로 실행 중인 컴퓨터의 다른 서비스에서 `net.pipe://localhost`를 수신하고 있습니다. 이 앱 설정을 `false`로 지정한 경우 클라이언트에서 잘못된 서비스에 연결하려고 시도합니다. 앱 설정을 `true`로 설정하면 클라이언트에서는 항상 가장 일치하는 서비스에 연결합니다.  
  
> [!NOTE]
>  클라이언트를 사용 하 여 <xref:System.ServiceModel.NetNamedPipeBinding> 대신 전체 끝점 주소 (있는 경우) 서비스의 기본 주소에 따라 서비스를 찾습니다. 이 설정을 항상 작동하게 하려면 서비스에서 고유 기준 주소를 사용해야 합니다.  
  
 이 변경을 사용하려면 클라이언트 응용 프로그램의 App.config 또는 Web.config 파일에 다음 앱 설정을 추가합니다.  
  
```xml  
  
<configuration>  
    <appSettings>  
        <add key="wcf:useBestMatchNamedPipeUri" value="true" />  
    </appSettings>  
</configuration>  
  
```  
  
 **SSL 3.0은 기본 프로토콜이 아닙니다.**  
 전송 보안 및 자격 증명 유형의 인증서를 지원하는 NetTcp를 사용할 경우 SSL 3.0은 더 이상 보안 연결을 협상하는 데 사용되는 기본 프로토콜이 아닙니다. 대부분의 경우 TLS 1.0이 NetTcp에 대한 프로토콜 목록에 포함되어 있으므로 기존 앱에는 영향을 주지 않습니다. 모든 기존 클라이언트에서는 TLS 1.0 이상을 사용하여 연결을 협상할 수 있습니다.      Ssl3가 필요한 경우 다음 구성 메커니즘 중 하나를 사용하여 협상된 프로토콜 목록에 Ssl3를 추가합니다.  
  
-   <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=fullName> 속성  
  
-   <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=fullName> 속성  
  
-   The [<>\>](../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md) section of the [<>\>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) section  
  
-   The [<>\>](../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) section of the [<>\>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) section  
  
<a name="WPF462"></a>   
### <a name="windows-presentation-foundation-wpf"></a>WPF(Windows Presentation Foundation)  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]에서 Windows Presentation Foundation이 다음과 같은 영역에서 향상되었습니다.  
  
 **그룹 정렬**  
 사용 하는 응용 프로그램을 <xref:System.Windows.Data.CollectionView> 이제 데이터를 그룹화 하는 개체 그룹을 정렬 하는 방법을 명시적으로 선언할 수 있습니다. 명시적으로 정렬하면 응용 프로그램에서 그룹을 동적으로 추가 또는 제거하거나 그룹화에 포함된 항목의 속성 값을 변경할 때 발생하는 직관적이지 않은 순서 지정 문제가 해결됩니다. 또한 그룹화 속성 비교를 전체 컬렉션 정렬에서 그룹화 정렬로 전환하여 그룹 만들기 프로세스의 성능을 향상할 수 있습니다.  
  
 그룹 정렬 지원 하기 위해 새 <xref:System.ComponentModel.GroupDescription.SortDescriptions%2A?displayProperty=fullName> 및 <xref:System.ComponentModel.GroupDescription.CustomSort%2A?displayProperty=fullName> 속성에 의해 생성 된 그룹의 컬렉션을 정렬 하는 방법을 설명는 <xref:System.ComponentModel.GroupDescription> 개체입니다. 이것은 동일 하 게 명명 되는 방식과 유사 <xref:System.Windows.Data.ListCollectionView> 속성 데이터 항목을 정렬 하는 방법에 설명 합니다.  
  
 새 정적 속성 두 개는 <xref:System.Windows.Data.PropertyGroupDescription> 클래스 <xref:System.Windows.Data.PropertyGroupDescription.CompareNameAscending%2A> 및 <xref:System.Windows.Data.PropertyGroupDescription.CompareNameDescending%2A>, 가장 일반적인 경우에 사용할 수 있습니다.  
  
 예를 들어 다음 XAML은 데이터를 연령별로 그룹화하고, 연령 그룹을 오름차순으로 정렬한 다음 각 연령 그룹 내의 항목을 성별로 그룹화합니다.  
  
```xaml  
  
<GroupDescriptions>  
     <PropertyGroupDescription   
         PropertyName=”Age”   
         CustomSort=   
              ”{x:Static PropertyGroupDescription.CompareNamesAscending}”/>  
     </PropertyGroupDescription>  
</GroupDescriptions>  
  
<SortDescriptions>  
     <SortDescription PropertyName=”LastName”/>  
</SortDescriptions>  
  
```  
  
 **소프트 키보드 지원**  
 소프트 키보드 지원을 사용하면 텍스트 입력을 수행할 수 있는 컨트롤을 통해 터치 입력을 수신할 때 Windows 10의 새로운 소프트 키보드를 자동으로 호출하거나 해제하여 WPF 응용 프로그램에서 포커스를 추적할 수 있습니다.  
  
 이전 버전 .NET Framework의 WPF 응용 프로그램에서는 포커스 추적을 사용하려면 WPF 펜/터치 제스처 지원을 사용하지 않도록 설정해야 합니다.  따라서 WPF 응용 프로그램에서는 전체 WPF 터치 지원을 선택하거나 Windows 마우스 승격을 사용해야 합니다.  
  
 **-모니터 DPI**  
 WPF 앱에 대해 최근에 확산되는 높은 DPI 및 하이브리드 DPI 환경을 지원하기 위해 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]의 WPF에서는 모니터별 인식을 사용하도록 지정합니다. 참조는 [샘플 및 개발자 가이드](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI) WPF 응용 프로그램을 사용 하는 방법에 대 한 자세한 내용은 github의-모니터 DPI를 인식 됩니다.  
  
 이전 버전의.NET Framework에서는 WPF 앱은 시스템 DPI를 인식합니다. 즉, 응용 프로그램의 UI는 앱이 렌더링되는 모니터의 DPI에 따라 OS에 의해 적절하게 확장됩니다. ,  
  
 아래에서 실행 되는 앱에 대 한는 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], 하는 구성 문을 추가 하 여 WPF 응용 프로그램의 변경 내용을 당 모니터 DPI 비활성화할 수는 [ <> \> ](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 다음과 같이 응용 프로그램 구성의 섹션 파일:  
  
```xml  
  
<runtime>  
   <AppContextSwitchOverrides value=”Switch.System.Windows.DoNotScaleForDpiChanges=false”/>  
</runtime>  
  
```  
  
<a name="WF462"></a>   
### <a name="windows-workflow-foundation-wf"></a>Windows WF(Workflow Foundation)  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]에서 Windows Workflow Foundation이 다음과 같은 영역에서 향상되었습니다.  
  
 **C# 식과 Re-hosted WF 디자이너의 IntelliSense에 대 한 지원**  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 이상에서 WF는 Visual Studio 디자이너와 코드 워크플로 모두에서 C# 식을 지원합니다. 다시 호스트된 워크플로 디자이너는 Visual Studio 외부 응용 프로그램(예: WPF)에서 워크플로 디자이너가 위치할 수 있도록 해주는 WF의 주요 기능입니다.  Windows Workflow Foundation을 사용하면 다시 호스트된 워크플로 디자이너에서 C# 식 및 IntelliSense를 지원할 수 있습니다. 자세한 내용은 참조는 [Windows Workflow Foundation 블로그](http://go.microsoft.com/fwlink/?LinkID=809042&clcid=0x409)합니다.  
  
 `Availability of IntelliSense when a customer rebuilds a workflow project from Visual Studio`  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 이전 버전의 .NET Framework에서는 고객이 Visual Studio에서 워크플로 프로젝트를 다시 작성할 때 WF Designer IntelliSense가 중단됩니다. 프로젝트 빌드에 성공 하 고 디자이너에 워크플로 유형을 찾을 수 없는 누락 된 워크플로 형식에 대 한 IntelliSense에서 경고에 표시 하는 동안는 **오류 목록** 창입니다. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]에서는 이 문제를 해결하고 IntelliSense를 사용할 수 있도록 해줍니다.  
  
 **워크플로 V1 응용 프로그램을 워크플로 추적 지금 FIPS 모드에서 실행**  
 이제 FIPS 호환성 모드를 사용하는 컴퓨터에서 워크플로 추적이 설정된 워크플로 버전 1 스타일 응용 프로그램을 실행할 수 있습니다. 이 시나리오를 사용하려면 app.config 파일을 다음과 같이 변경해야 합니다.  
  
```xml  
<add key="microsoft:WorkflowRuntime:FIPSRequired" value="true" />  
```  
  
 이 시나리오를 사용하지 않도록 설정한 경우 응용 프로그램을 실행하면 계속해서 예외가 발생하고 “이 구현은 Windows Platform FIPS 유효성을 검사한 암호화 알고리즘의 일부가 아닙니다.”라는 메시지가 표시됩니다.  
  
 **Visual Studio 워크플로 디자이너와 동적 업데이트를 사용 하는 경우 워크플로 기능 향상**  
 워크플로 디자이너, 순서도 활동 디자이너 및 기타 워크플로 활동 디자이너 이제 성공적으로 로드 하 고 표시 호출한 후 저장 된 워크플로 <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=fullName> 메서드. 하기 전에.NET Framework의 버전에는 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 호출한 후 저장 된 워크플로에 대 한 Visual Studio에서 XAML 파일을 로드할 <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=fullName> 다음과 같은 문제가 발생할 수 있습니다.  
  
-   워크플로 디자이너는 XAML 파일을 올바르게 로드할 수 없습니다 (때는 <xref:System.Activities.Presentation.ViewState.ViewStateData.Id%2A?displayProperty=fullName> 줄의 끝에).  
  
-   순서도 활동 디자이너 또는 기타 워크플로 활동 디자이너는 연결된 속성 값과 달리 모든 개체를 기본 위치에 표시할 수 있습니다.  
  
<a name="ClickOnce"></a>   
### <a name="clickonce"></a>ClickOnce  
 ClickOnce는 이미 지원되는 1.0 프로토콜 외에 TLS 1.1 및 TLS 1.2를 지원하도록 업데이트되었습니다. ClickOnce는 필요한 프로토콜을 자동으로 검색하므로, TLS 1.1 및 1.2 지원하기 위해 ClickOnce 응용 프로그램에서 별도의 단계를 수행할 필요가 없습니다.  
  
<a name="UWPConvert"></a>   
### <a name="converting-windows-forms-and-wpf-apps-to--uwp-apps"></a>Windows Forms 및 WPF 앱을 UWP 앱으로 변환  
 이제 Windows에서는 기존 Windows 데스크톱 앱(예: WPF 및 Windows Forms 앱)을 UWP(유니버설 Windows 플랫폼)로 가져올 수 있습니다. 이 기술은 기존 코드 베이스를 UWP로 점차적으로 마이그레이션하여 앱을 모든 Windows 10 장치로 가져옴으로써 브리지 역할을 합니다.  
  
 변환된 데스크톱 앱은 UWP 앱의 ID와 비슷한 앱 ID를 얻습니다. 이 ID를 사용하여 UWP API에 액세스하여 라이브 타일, 알림 등과 같은 기능을 사용할 수 있습니다. 앱은 이전과 동일하게 작동하고 완전히 신뢰할 수 있는 앱으로 실행됩니다. 앱이 변환되면 기존 완전 신뢰 프로세스에 앱 컨테이너 프로세스를 추가하여 적응형 사용자 인터페이스를 추가할 수 있습니다. 모든 기능을 앱 컨테이너 프로세스로 이동한 후 완전 신뢰 프로세스를 제거하고 모든 Windows 10 장치에서 새 UWP 앱을 사용할 수 있습니다.  
  
<a name="Debug462"></a>   
### <a name="debugging-improvements"></a>디버깅 기능 향상  
 *관리 되지 않는 디버깅 API* 개선 되었습니다는 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 추가 분석을 수행 하려면 때는 <xref:System.NullReferenceException> 예외가 발생 한 소스 코드 줄에 있는 변수는 확인할 수 있도록 `null`합니다.   이 시나리오를 지원하기 위해 관리되지 않는 디버깅 API에 다음 API를 추가했습니다.  
  
-   [ICorDebugCode4](../../../ocs/framework/unmanaged-api/debugging/icordebugcode4-interface.md), [ICorDebugVariableHome](../../../ocs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md), 및 [ICorDebugVariableHomeEnum](../../../ocs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) 노출 관리 되는 변수의 네이티브 가정 하는 인터페이스입니다. 이 통해 몇 가지 코드 흐름을 분석 하는 작업을 수행 하는 디버거 때는 <xref:System.NullReferenceException> 발생 된 기본 위치에 해당 하는 관리 되는 변수를 확인 하기 위해 이전 버전과 작동 하도록 하 고 `null`합니다.  
  
-   [ICorDebugType2::GetTypeID](../Topic/ICorDebugType2::GetTypeID%20Method.md) 메서드를 ICorDebugType에 대 한 매핑을 제공 [COR_TYPEID](../../../ocs/framework/unmanaged-api/debugging/cor-typeid-structure.md), 디버거를 가져올 수 있는 한 [COR_TYPEID](../../../ocs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 는 ICorDebugType의 인스턴스 없이도 합니다. 기존 Api에 [COR_TYPEID](../../../ocs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 형식의 클래스 레이아웃을 결정 사용할 수 있습니다.  
  
<a name="v461"></a>   
## <a name="whats-new-in-the-net-framework-461"></a>.NET Framework 4.6.1의 새로운 기능  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에는 다음과 같은 영역의 새 기능이 포함됩니다.  
  
-   [암호화](#Crypto)  
  
-   [ADO.NET](#ADO.NET461)  
  
-   [Windows Presentation Foundation (WPF)](#WPF461)  
  
-   [Windows Workflow Foundation](#WWF461)  
  
-   [프로 파일링](#Profile461)  
  
-   [NGen](#NGEN461)  
  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
-   [변경 내용 목록은.NET Framework 4.6.1](http://go.microsoft.com/fwlink/?LinkId=622964)  
  
-   [4.6.1의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)  
  
-   [.NET Framework API 차이점](http://go.microsoft.com/fwlink/?LinkId=622989) (GitHub)에서  
  
<a name="Crypto"></a>   
### <a name="cryptography-support-for-x509-certificates-containing-ecdsa"></a>암호화: ECDSA를 포함하는 X509 인증서 지원  
 .NET Framework 4.6에는 x509 인증서를 위한 RSACng 지원이 추가되었습니다. [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에는 ECDSA(타원 곡선 디지털 서명 알고리즘) X509 인증서에 대한 지원이 추가되었습니다.  
  
 ECDSA는 RSA보다 더 향상된 성능과 더 안전한 암호화 알고리즘을 제공하므로 TLS(전송 계층 보안) 성능 및 확장성 면에서 최고의 선택이 될 것입니다. .NET Framework 구현은 기존 Windows 기능으로 호출을 래핑합니다.  
  
 다음 예제 코드에서는 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에 포함된 ECDSA  X509 인증서에 대한 새 지원을 사용하여 바이트 스트림을 위한 서명을 쉽게 생성하는 방법을 보여 줍니다.  
  
 [!code-csharp[whatsnew.461.crypto#1](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#1)]
 [!code-vb[whatsnew.461.crypto#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code461.vb#1)]  
  
 다음은 .NET Framework 4.6에서 서명을 생성하는 데 필요한 코드에 표시된 대비를 제공합니다.  
  
 [!code-csharp[whatsnew.461.crypto#2](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#2)]
 [!code-vb[whatsnew.461.crypto#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code46.vb#2)]  
  
<a name="ADO.NET461"></a>   
### <a name="adonet"></a>ADO.NET  
 ADO.NET에는 다음이 추가되었습니다.  
  
 하드웨어로 보호된 키에 대해 상시 암호화 지원  
 ADO.NET은 이제 상시 암호화 열 마스터 키를 HSM(하드웨어 보안 모듈)에 고유하게 저장할 수 있습니다. 이 지원을 통해 고객은 사용자 지정 열 마스터 키 저장소 공급자를 작성하고 응용 프로그램에 등록하지 않고도 HSM에 저장된 비동기 키를 활용할 수 있습니다.  
  
 HSM에 저장된 열 마스터 키로 보호된 상시 암호화 데이터에 액세스하려면 고객이 HSM 공급업체에서 제공한 CSP 공급자 또는 CNG 키 저장소 공급자를 앱 서버 또는 클라이언트 컴퓨터에 설치해야 합니다.  
  
 개선 <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> AlwaysOn에 대 한 연결 동작  
 SqlClient는 이제 자동으로 AlwaysOn AG(가용성 그룹)에 대한 더 빠른 연결을 제공합니다. 응용 프로그램이 다른 서브넷의 AlwaysOn AG(가용성 그룹)에 연결되었는지 투명하게 감지하고 현재 활성 서버를 신속하게 검색하여 서버에 대한 연결을 제공합니다. 이 릴리스 전에는 AlwaysOn 가용성 그룹에 연결되었음을 나타내기 위해 응용 프로그램에서 `“MultisubnetFailover=true”`를 포함하도록 연결 문자열을 설정해야 했습니다. 연결 키워드를 `true`로 설정하지 않은 경우 응용 프로그램에서 AlwaysOn 가용성 그룹에 연결하는 동안 시간 초과가 발생할 수 있습니다. 응용 프로그램에서는이 릴리스와 함께 *하지* 설정 해야 할 <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> 를 `true` 더 이상. Alwayson 가용성 그룹의 SqlClient 지원에 대 한 자세한 내용은 참조 [고가용성 및 재해 복구에 대 한 SqlClient 지원](../../../docs/framework/data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md)합니다.  
  
<a name="WPF461"></a>   
### <a name="windows-presentation-foundation-wpf"></a>WPF(Windows Presentation Foundation)  
 Windows Presentation Foundation에는 많은 향상된 기능 및 변경 내용이 포함되어 있습니다.  
  
 향상된 성능  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에서 터치 이벤트를 발생시킬 때의 지연이 수정되었습니다. 또한,를 입력 하는 <xref:System.Windows.Controls.RichTextBox> 제어 더 이상 연결 하면 렌더링 스레드 빠른 입력 하는 동안.  
  
 맞춤법 검사 향상  
 Windows 8.1 이상 버전에서는 추가 언어 맞춤법 검사에 대한 운영 체제 지원을 사용하도록 WPF의 맞춤법 검사기 기능이 업데이트되었습니다.  Windows 8.1 이전의 Windows 버전에 대해서는 기능이 변경되지 않았습니다.  
  
 이전 버전의.NET Framework에 대 한 언어와는 <xref:System.Windows.Controls.TextBox> 또는 제어 <xref:System.Windows.Controls.RichTextBox> 블록 정보는 다음 순서 대로 검색:  
  
-   `xml:lang`(있는 경우)  
  
-   현재 입력 언어  
  
-   현재 스레드 문화권  
  
 WPF의 언어 지원에 대 한 자세한 내용은 참조는 [4.6.1.NET Framework 기능에 WPF 블로그 게시물](http://go.microsoft.com/fwlink/?LinkID=691819)합니다.  
  
 사용자 단위 사용자 지정 사전에 대한 추가 지원  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에서 WPF는 전역으로 등록된 사용자 지정 사전을 인식합니다. 컨트롤 단위로 등록하는 기능 외에 이 기능을 사용할 수 있습니다.  
  
 WPF 이전 버전에서는 사용자 지정 사전에서 제외된 단어 및 자동 고침 목록을 인식하지 못했습니다. Windows 8.1 및 Windows 10에서는 `%AppData%\Microsoft\Spelling\<language tag>` 디렉터리에 저장할 수 있는 파일을 사용하여 이러한 기능이 지원됩니다.  이러한 파일에 적용되는 규칙은 다음과 같습니다.  
  
-   파일의 확장명은 .dic(추가된 단어용), .exc(제외된 단어용) 또는 .acl(자동 고침용)입니다.  
  
-   파일은 BOM(바이트 순서 표시)으로 시작하는 UTF-16 LE 일반 텍스트여야 합니다.  
  
-   (추가 되 고 제외 된 단어 목록)에서 단어의 각 줄에 포함 해야 또는 세로 막대로 구분 된 단어는 자동 고침 쌍 ("|") (자동 고침 단어 목록에서).  
  
-   이러한 파일은 읽기 전용으로 간주되며 시스템에 의해 수정되지 않습니다.  
  
> [!NOTE]
>  이러한 새 파일 형식은 WPF 맞춤법 검사 API에 의해 직접 지원되지 않으며 응용 프로그램에서 WPF에 제공된 사용자 지정 사전은 계속 .lex 파일을 사용해야 합니다.  
  
 샘플  
 여러 가지 [WPF 샘플](https://msdn.microsoft.com/library/ms771633.aspx) MSDN에 있습니다. 가장 인기 있는 샘플 (용도에 따라) 200 개 이상의 이동 됩니다는 [오픈 소스 GitHub 리포지토리](https://github.com/Microsoft/WPF-Samples)합니다. 끌어오기 요청 또는 여는 우리를 전송 하 여 샘플 개선에 참여 한 [GitHub 문제](https://github.com/Microsoft/WPF-Samples/issues)합니다.  
  
 DirectX 확장  
 WPF에서는 [NuGet 패키지](http://go.microsoft.com/fwlink/?LinkID=691342) 의 새 구현을 제공 하는 <xref:System.Windows.Interop.D3DImage> 는 쉽게 DX10 및 Dx11와 상호 운용할 수에 대 한 콘텐츠입니다. 코드는이 패키지는 열려 있기에 대 한 원본으로 제공 되며 사용할 수 [github](https://github.com/Microsoft/WPFDXInterop)합니다.  
  
<a name="WWF461"></a>   
### <a name="windows-workflow-foundation-transactions"></a>Windows Workflow Foundation: 트랜잭션  
 <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=fullName> 메서드는 분산된 트랜잭션 관리자 MSDTC 이외의 트랜잭션을 승격을 이제 사용할 수 있습니다. 이렇게 하면 새 트랜잭션 프로모터 GUID 식별자를 지정 하 여 <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=fullName> 오버 로드 합니다. 이 작업이 성공한 경우 트랜잭션 기능이 제한됩니다. 비 MSDTC 트랜잭션 프로모터는 참여 하 고, 다음 메서드를 throw 한 <xref:System.Transactions.TransactionPromotionException> 이러한 메서드는 MSDTC로의 승격은 필요 하기 때문에:  
  
-   <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=fullName>  
  
-   <xref:System.Transactions.TransactionInterop.GetDtcTransaction%2A?displayProperty=fullName>  
  
-   <xref:System.Transactions.TransactionInterop.GetExportCookie%2A?displayProperty=fullName>  
  
-   <xref:System.Transactions.TransactionInterop.GetTransmitterPropagationToken%2A?displayProperty=fullName>  
  
 비 MSDTC 트랜잭션 프로모터가 등록된 경우 향후 정의된 프로토콜을 사용하여 지속적인 인리스트먼트에 사용되어야 합니다. <xref:System.Guid> 트랜잭션 프로모터 사용 하 여 가져올 수는 <xref:System.Transactions.Transaction.PromoterType%2A> 속성입니다. 경우 트랜잭션이 승격, 트랜잭션 프로모터 제공는 <xref:System.Byte> 승격 된 토큰을 나타내는 배열입니다. 응용 프로그램에 대 한 비 MSDTC 승격 트랜잭션의 대 한 승격 된 토큰을 가져올 수는 <xref:System.Transactions.Transaction.GetPromotedToken%2A> 메서드.  
  
 사용자가 새 <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=fullName> 오버 로드 프로 모션 작업을 성공적으로 완료 하기 위해 특정 호출 순서를 따라야 합니다. 이러한 규칙은 메서드 설명서에 나와 있습니다.  
  
<a name="Profile461"></a>   
### <a name="profiling"></a>프로파일링  
 관리되지 않는 프로파일링 API가 다음과 같이 개선되었습니다.  
  
 Pdb에 액세스 하는 것에 대 한 지원 향상 된 [ICorProfilerInfo7](../../../ocs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) 인터페이스  
 ASP.Net 5에서는 Roslyn에 의해 어셈블리가 메모리 내에서 컴파일되는 일이 더 많아지고 있습니다. 프로파일링 도구를 만드는 개발자에게 있어 이는 지금까지 디스크에 serialize되던 PDB가 더 이상 존재하지 않는다는 의미입니다. 프로파일러 도구는 종종 코드 검사 또는 줄 단위 성능 분석 등의 작업을 위해 PDB를 사용하여 코드를 다시 소스 줄에 매핑합니다. [ICorProfilerInfo7](../../../ocs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) 인터페이스는 이제 두 개의 새로운 메서드 포함 [ICorProfilerInfo7::GetInMemorySymbolsLength](../Topic/ICorProfilerInfo7::GetInMemorySymbolsLength%20Method.md) 및 [ICorProfilerInfo7::ReadInMemorySymbols](../Topic/ICorProfilerInfo7::ReadInMemorySymbols.md), 메모리 내 PDB 데이터에 액세스할 수 있는 이러한 프로파일러 도구를 제공 하는 새로운 Api를 사용 하 여 프로파일러 수 바이트 배열로 메모리 내 PDB의 내용을 가져오는 다음 처리 하거나 디스크에 serialize 합니다.  
  
 ICorProfiler 인터페이스를 사용하여 계측 향상  
 동적 계측을 위해 `ICorProfiler` API의 ReJit 기능을 사용하는 프로파일러는 이제 일부 메타데이터를 수정할 수 있습니다. 이전에는 이러한 도구를 사용하여 언제든지 IL을 계측할 수 있었지만 메타데이터는 모듈 로드 시에만 수정할 수 있었습니다. IL은 메타데이터를 참조하므로 수행할 수 있는 계측 종류에 한계가 있었습니다. 우리 늘어났으며 이러한 제한을 추가 하 여는 [ICorProfilerInfo7::ApplyMetaData](../Topic/ICorProfilerInfo7::ApplyMetaData%20Method.md) 로드 되 면 모듈, 특히 새로운를 추가 하 여 메타 데이터 편집의 하위 집합을 지원 하기 위해 메서드에 `AssemblyRef`, `TypeRef`, `TypeSpec`, `MemberRef`, `MemberSpec`, 및 `UserString` 레코드입니다. 이 변경을 통해 즉시 계측의 범위가 더 넓어졌습니다.  
  
<a name="NGEN461"></a>   
### <a name="native-image-generator-ngen-pdbs"></a>NGEN(네이티브 이미지 생성기) PDB  
 컴퓨터 간 이벤트 추적을 사용하면 고객이 시스템 A에서 프로그램을 프로파일링하고 소스 줄 매핑을 사용하여 시스템 B에서 프로파일링 데이터를 확인할 수 있습니다. 이전 버전의 .NET Framework에서는 사용자가 프로파일링된 시스템의 모든 모듈 및 네이티브 이미지를 IL PDB가 포함된 분석 시스템으로 복사하여 원본-네이티브 매핑을 만들었습니다. 이 프로세스는 휴대폰 응용 프로그램 등 비교적 파일이 작은 경우에는 잘 작동하지만 데스크톱 시스템에서는 파일이 매우 커질 수 있으며 복사하는 데 많은 시간이 필요합니다.  
  
 Ngen PDB를 사용하면 NGen이 IL PDB에 대한 종속성 없이 IL-네이티브 매핑이 포함된 PDB를 만들 수 있습니다. 컴퓨터 간 이벤트 추적 시나리오에서는 필요한 모든 작업이 컴퓨터 B로 A 컴퓨터에서 생성 되는 PDB는 네이티브 이미지를 복사 하를 사용 하는 [디버그 인터페이스 액세스 Api](https://msdn.microsoft.com/en-us/library/ee8x173s.aspx) IL PDB의 IL을 소스 매핑 및 네이티브 이미지 PDB IL-네이티브 매핑 읽을 수 있습니다. 두 매핑을 함께 사용하면 소스-네이티브 매핑이 생성됩니다. 네이티브 이미지 PDB는 모든 모듈 및 네이티브 이미지보다 훨씬 작으므로 시스템 A에서 시스템 B로 복사하는 프로세스가 훨씬 빨라집니다.  
  
<a name="v46"></a>   
## <a name="whats-new-in-net-2015"></a>.NET 2015의 새로운 기능  
 .NET 2015에서는 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 및 .NET Core가 도입되었습니다. 일부 새로운 기능은 둘 다에 적용되고 기타 기능은 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 또는 [!INCLUDE[net_core](../../../includes/net-core-md.md)] 중 하나와 관련이 있습니다.  
  
-   **ASP.NET 5**  
  
     .NET 2015에는 최신 클라우드 기반 앱을 빌드하기 위한 린(lean) .NET 플랫폼인 ASP.NET 5가 포함되어 있습니다. 이 플랫폼은 모듈식이므로 응용 프로그램에 필요한 기능만 포함할 수 있습니다. IIS에서 호스트되거나 사용자 지정 프로세스에서 자체 호스트될 수 있으며 동일한 서버에서 다양한 .NET Framework 버전으로 앱을 실행할 수 있습니다. 클라우드 배포용으로 설계된 새 환경 구성 시스템도 포함됩니다.  
  
     MVC, Web API 및 웹 페이지가 MVC 6이라는 단일 프레임워크로 통합됩니다. Visual Studio 2015의 새로운 도구를 통해 ASP.NET 5 앱을 빌드합니다. 기존 응용 프로그램도 새로운 .NET Framework에서 작동하지만 MVC 6 또는 SignalR 3을 사용하는 앱을 빌드하려면 Visual Studio 2015의 프로젝트 시스템을 사용해야 합니다.  
  
     내용은 [ASP.NET 5](http://go.microsoft.com/fwlink/?LinkId=518238)합니다.  
  
-   **ASP.NET 업데이트**  
  
    -   **비동기 응답 플러시에 대 한 작업 기반 API**  
  
         이제 ASP.NET 비동기 응답 플러시에 대 한 간단한 작업 기반 API를 제공 <xref:System.Web.HttpResponse.FlushAsync%2A?displayProperty=fullName>, 해당 언어를 사용 하 여 비동기적으로 플러시할 수에 대 한 응답 수 있게 해 주는 `async/await` 지원 합니다.  
  
    -   `Model binding supports task-returning methods`  
  
         [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에 ASP.NET이 Web Forms 페이지 및 사용자 정의 컨트롤에서 CRUD 기반 데이터 작업으로 확장 가능하고 코드 중심의 접근이 가능하도록 모델 바인딩 기능을 추가했습니다. 모델 바인딩 시스템 이제 지원 <xref:System.Threading.Tasks.Task>-모델 바인딩 메서드가 반환 합니다. 이 기능으로 Web Forms 개발자가 Entity Framework를 포함하여 새 버전의 ORM을 사용하는 경우 간편한 데이터 바인딩 시스템과 함께 비동기의 확장성 이점을 얻을 수 있습니다.  
  
         비동기 모델 바인딩은 `aspnet:EnableAsyncModelBinding` 구성 설정으로 제어합니다.  
  
        ```  
  
        <appSettings>  
           <add key=" aspnet:EnableAsyncModelBinding" value="true|false" />  
        </appSettings>  
  
        ```  
  
         [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]을 대상으로 하는 앱에서는 기본적으로 `true`입니다. 이전 버전의 .NET Framework를 대상으로 하고 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]에서 실행되는 앱에서는 기본적으로 `false`입니다. 구성을 `true`로 설정하여 사용할 수 있습니다.  
  
    -   **HTTP/2 지원 (Windows 10)**  
  
         [HTTP/2](http://www.wikipedia.org/wiki/HTTP/2) 낮은 웹 페이지 로딩 대기 시간 사용자에 대 한 결과 더 나은 연결 사용률 (왕복 횟수 감소 클라이언트와 서버 간에)을 제공 하는 HTTP 프로토콜의 새 버전입니다.  이 프로토콜은 단일 환경의 일부로 요청되는 여러 아티팩트에 최적화되었으므로 웹 페이지(서비스 대비)가 HTTP/2에서 가장 많은 혜택을 얻을 수 있습니다. .NET Framework 4.6의 ASP.NET에는 HTTP/2 지원이 추가되었습니다. 여러 레이어에 네트워킹 기능이 있기 때문에 HTTP/2를 사용하려면 Windows, IIS 및 ASP.NET에 새로운 기능이 필요했습니다. ASP.NET과 함께 HTTP/2를 사용하려면 Windows 10에서 실행해야 합니다.  
  
         HTTP/2도 지원 하 고에 기본적으로 windows 10 유니버설 Windows 플랫폼 UWP () 앱을 사용 하 여 <xref:System.Net.Http.HttpClient?displayProperty=fullName> API입니다.  
  
         사용 하는 방법을 제공 하기 위해는 [PUSH_PROMISE](http://http2.github.io/http2-spec/#PUSH_PROMISE) 기능을 ASP.NET 응용 프로그램에서는 두 개의 오버 로드는 새 메서드 <xref:System.Web.HttpResponse.PushPromise%28System.String%29> 및 <xref:System.Web.HttpResponse.PushPromise%28System.String%2CSystem.String%2CSystem.Collections.Specialized.NameValueCollection%29>를에 추가 되었습니다는 <xref:System.Web.HttpResponse> 클래스입니다.  
  
        > [!NOTE]
        >  ASP.NET 5는 HTTP/2를 지원하는 반면 PUSH PROMISE 기능에 대한 지원은 아직 추가되지 않았습니다.  
  
         브라우저와 웹 서버(Windows의 IIS)가 모든 작업을 수행합니다. 사용자를 위해 직접 힘든 작업을 수행할 필요가 없습니다.  
  
         대부분의 [주요 브라우저는 HTTP/2 지원](http://www.wikipedia.org/wiki/HTTP/2), 서버에서 지원할 경우 HTTP/2 지원에서 사용자에 게 도움이 될 가능성이 있기 때문입니다.  
  
    -   **토큰 바인딩 프로토콜에 대 한 지원**  
  
         Microsoft 및 Google 인증을 호출 하는 새로운 방법에서 작업의 [토큰 바인딩 프로토콜](https://github.com/TokenBinding/Internet-Drafts)합니다. 전제 (브라우저 캐시)의 인증 토큰 도난 및 암호 또는 기타 권한 있는 지식을 요구 하지 않고 범죄자 보안 리소스 (예: 은행 계좌)에 액세스 하 여 사용할 수 있습니다 것입니다. 새 프로토콜은 이 문제를 완화시키기 위한 것입니다.  
  
         토큰 바인딩 프로토콜은 Windows 10에서 브라우저 기능으로 구현됩니다. 인증 토큰이 정당한 것으로 검증되도록 ASP.NET 앱이 프로토콜에 참여합니다. 클라이언트와 서버 구현은 프로토콜에 의해 지정된 종단 간 보호를 설정합니다.  
  
    -   **임의 문자열 해시 알고리즘**  
  
         도입 하는.NET Framework 4.5는 [임의 문자열 해시 알고리즘](https://msdn.microsoft.com/library/jj152924.aspx)합니다. 그러나 일부 ASP.NET 기능이 안정적인 해시 코드에 종속되어 있어 ASP.NET에서는 지원하지 않았습니다. 이제 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]에서 임의 문자열 해시 알고리즘을 지원합니다. 이 기능을 사용하려면 `aspnet:UseRandomizedStringHashAlgorithm` 구성 설정을 사용합니다.  
  
        ```  
  
        <appSettings>  
           <add key="aspnet:UseRandomizedStringHashAlgorithm" value="true|false" />  
        </appSettings>  
  
        ```  
  
-   **ADO.NET**  
  
     ADO .NET은 이제 SQL Server 2016 CTP2(Community Technology Preview 2)에서 제공되는 상시 암호화 기능을 지원합니다. 항상 암호화 기능을 사용하면 SQL Server는 암호화된 데이터에 대해 작업을 수행할 수 있으며 무엇보다도, 암호화 키는 서버가 아니라 고객의 신뢰할 수 있는 환경 내에서 응용 프로그램과 함께 상주합니다. 항상 암호화 기능은 DBA가 일반 텍스트 데이터에 액세스할 수 없도록 고객 데이터를 보호합니다. 데이터 암호화 및 암호 해독은 드라이버 수준에서 투명하게 이루어지며 기존 응용 프로그램에 대한 변경을 최소화합니다. 자세한 내용은 다음을 참조 하십시오. [항상 암호화 됩니다 (데이터베이스 엔진)](https://msdn.microsoft.com/library/mt163865\(v=sql.130\).aspx) 및 [항상 암호화 됩니다 (클라이언트 개발)](https://msdn.microsoft.com/library/mt147923\(v=sql.130\).aspx)합니다.  
  
-   **관리 코드에 대 한&64; 비트 JIT 컴파일러**  
  
     .NET Framework 4.6에는 새 버전의64비트 JIT 컴파일러(원래 코드 이름은 RyuJIT)가 있습니다. 새로운 64비트 컴파일러는 이전 64비트 JIT 컴파일러보다 훨씬 향상된 성능을 제공합니다. 새로운 64비트 컴파일러는 .NET Framework 4.6에서 실행되는 64비트 프로세스에 사용됩니다. 앱이 64비트 또는 AnyCPU로 컴파일되고 64비트 운영 체제에서 실행되는 경우 해당 앱은 64비트 프로세스에서 실행됩니다. 새 컴파일러로 전환할 때 무슨 조치를 취했는지 투명하게 알 수 있으면 동작을 변경할 수 있습니다. 새 JIT 컴파일러를 사용할 때 발생하는 모든 문제에 대해 직접 듣고 싶습니다. 통해 연락해 주십시오 [Microsoft Connect](http://connect.microsoft.com/) 새로운 64 비트 JIT 컴파일러에 관련 될 수 있는 문제가 발생 하는 경우.  
  
     새로운 64 비트 JIT 컴파일러에도 하드웨어 SIMD 가속 기능에 대 한 SIMD 사용 형식와 결합 하면는 <xref:System.Numerics> 네임 스페이스에 좋은 성능 향상을 얻을 수 있습니다.  
  
-   **어셈블리 로더 개선**  
  
     이제 어셈블리 로더가 해당 NGEN 이미지를 로드한 후 IL 어셈블리를 언로드하여 보다 효율적으로 메모리를 사용합니다. 이 변경으로 가상 메모리가 감소됩니다. 특히 큰 32비트 앱(예: Visual Studio)에 대해 효과적이며 실제 메모리도 절약됩니다.  
  
-   **기본 클래스 라이브러리 변경 내용**  
  
     주요 시나리오를 사용할 수 있도록 많은 API가 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]에 새로 추가되었습니다. 변경 및 추가된 내용은 다음과 같습니다.  
  
    -   **IReadOnlyCollection<> \</> \> 구현**  
  
         추가 컬렉션 구현 <xref:System.Collections.Generic.IReadOnlyCollection%601> 와 같은 <xref:System.Collections.Generic.Queue%601> 및 <xref:System.Collections.Generic.Stack%601>합니다.  
  
    -   **CultureInfo.CurrentCulture 및 CultureInfo.CurrentUICulture**  
  
         <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 속성이 읽기 / 쓰기 보다는 읽기 전용으로 설정 됩니다. 새 할당 하는 경우 <xref:System.Globalization.CultureInfo> 이러한 속성에 정의 된 현재 스레드 문화권에 대 한 개체는 `Thread.CurrentThread.CurrentCulture` 속성의 현재 UI 스레드 문화권에 정의 된는 `Thread.CurrentThread.CurrentUICulture` 속성을 변경할 수도 있습니다.  
  
    -   **가비지 수집 (GC) 향상**  
  
         <xref:System.GC> 클래스에 포함 되어 이제 <xref:System.GC.TryStartNoGCRegion%2A> 및 <xref:System.GC.EndNoGCRegion%2A> 중요 한 경로 실행 하는 동안 가비지 수집을 차단할 수 있도록 하는 방법입니다.  
  
         새 오버 로드는 <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%2CSystem.Boolean%29?displayProperty=fullName> 메서드 제어할 수 있는 소형 개체 힙과 대형 개체 힙을 모두 정리 및 압축 인지 정리만 여부.  
  
    -   **SIMD 사용 형식**  
  
         <xref:System.Numerics> 네임 스페이스 이제 포함 된 다양 한 SIMD 사용 형식 예: <xref:System.Numerics.Matrix3x2>, <xref:System.Numerics.Matrix4x4>, <xref:System.Numerics.Plane>, <xref:System.Numerics.Quaternion>, <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3>, 및 <xref:System.Numerics.Vector4>합니다.  
  
         또한 새로운 64비트 JIT 컴파일러에는 하드웨어 SIMD 가속 기능이 있으므로 SIMD 사용 형식과 새 64비트 JIT 컴파일러를 함께 사용하면 성능이 현저히 향상됩니다.  
  
    -   **암호화 업데이트**  
  
         <xref:System.Security.Cryptography?displayProperty=fullName> API 지원 하도록 업데이트 되는 [Windows CNG 암호화 Api](https://msdn.microsoft.com/library/windows/desktop/aa376214.aspx)합니다. 이전 버전의.NET Framework에 완전히 사용해왔습니다는 [이전 버전의 Windows 암호화 Api](https://msdn.microsoft.com/library/windows/desktop/aa380255.aspx) 에 대 한 기준으로는 <xref:System.Security.Cryptography?displayProperty=fullName> 구현 합니다. 지원 하기 때문에 CNG API를 지원 하기 위해 요청 [최신 암호화 알고리즘](https://msdn.microsoft.com/library/windows/desktop/bb204775.aspx#suite_b_support), 특정 범주의 앱에 대 한 중요 한 합니다.  
  
         .NET Framework 4.6에는 Windows CNG 암호화 API를 지원하는 다음과 같은 새로운 향상 기능이 포함되어 있습니다.  
  
        -   X509 인증서에 대한 일련의 확장 메서드(`System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` 및 `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)`) - 가능한 경우 CAPI 기반 구현 대신 CNG 기반 구현을 반환합니다. (일부 스마트 카드 등에는 여전히 CAPI가 필요하며 API가 대체(fallback) 처리합니다.)  
  
        -   <xref:System.Security.Cryptography.RSACng?displayProperty=fullName> RSA 알고리즘의 CNG 구현을 제공 하는 클래스입니다.  
  
        -   RSA API에 대한 향상 기능 - 일반 작업에 더 이상 캐스팅이 필요하지 않습니다. 예를 들어, 다음을 사용 하 여 데이터를 암호화 한 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 개체는 이전 버전의.NET Framework에서 다음과 같은 코드를 필요 합니다.  
  
             [!code-csharp[WhatsNew.Casting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#1)]
             [!code-vb[WhatsNew.Casting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#1)]  
  
             .NET Framework 4.6에서 새로운 암호화 API를 사용하는 코드는 캐스팅을 방지하기 위해 다음과 같이 작성될 수 있습니다.  
  
             [!code-csharp[WhatsNew.Casting#2](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#2)]
             [!code-vb[WhatsNew.Casting#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#2)]  
  
    -   **Unix 시간 날짜 및 시간 변환에 대 한 지원**  
  
         에 추가 된 다음과 같은 새 메서드는 <xref:System.DateTimeOffset> 과 Unix 시간 날짜 및 시간 값을 변환 하는 지 원하는 구조:  
  
        -   <xref:System.DateTimeOffset.FromUnixTimeSeconds%2A?displayProperty=fullName>  
  
        -   <xref:System.DateTimeOffset.FromUnixTimeMilliseconds%2A?displayProperty=fullName>  
  
        -   <xref:System.DateTimeOffset.ToUnixTimeSeconds%2A?displayProperty=fullName>  
  
        -   <xref:System.DateTimeOffset.ToUnixTimeMilliseconds%2A?displayProperty=fullName>  
  
    -   **호환성 스위치**  
  
         새 <xref:System.AppContext> 클래스 라이브러리 작성자가 사용자를 위한 새로운 기능에 대 한 균일 한 옵트아웃 메커니즘을 제공할 수 있도록 새 호환성 기능을 추가 합니다. 옵트아웃(opt out) 요청을 전달하기 위해 구성 요소 간에 느슨하게 결합된 계약을 설정합니다. 이 기능은 일반적으로 기존 기능이 변경될 때 중요합니다. 반대로, 새로운 기능에 대한 암시적 옵트인(opt in)은 이미 있습니다.  
  
         와 <xref:System.AppContext>, 라이브러리 정의 및 노출 호환성 스위치를 코드에 의존 하는 동안 해당 스위치를 라이브러리 동작에 영향을 설정할 수 있습니다. 기본적으로 라이브러리는 새로운 기능을 제공하며 스위치가 설정된 경우에만 변경합니다(즉, 이전 기능 제공).  
  
         응용 프로그램 (또는 라이브러리) 스위치의 값을 선언할 수 있습니다 (항상는 <xref:System.Boolean> 값)은 종속 라이브러리가 정의 하는 합니다. 스위치는 암시적으로 항상 `false`입니다. 스위치를 `true`로 설정하면 사용할 수 있습니다. 스위치를 명시적으로 `false`로 설정하면 새 동작이 제공됩니다.  
  
        ```csharp  
        AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", true);  
        ```  
  
         라이브러리는 소비자가 스위치 값을 선언했는지 확인한 다음 적절하게 동작해야 합니다.  
  
        ```  
  
        if (!AppContext.TryGetSwitch("Switch.AmazingLib.ThrowOnException", out shouldThrow))   
        {  
           // This is the case where the switch value was not set by the application.   
           // The library can choose to get the value of shouldThrow by other means.   
           // If no overrides nor default values are specified, the value should be 'false'.   
           // A false value implies the latest behavior.  
        }  
  
           // The library can use the value of shouldThrow to throw exceptions or not.  
           if (shouldThrow)   
           {  
              // old code  
           }  
           else {  
              // new code  
           }  
        }  
  
        ```  
  
         라이브러리에 의해 노출되는 공식 계약이므로 스위치에 대해 일관된 형식을 사용하는 것이 좋습니다. 다음은 두 가지 명확한 형식입니다.  
  
        -   *Switch*.* 네임 스페이스*.* switchname*  
  
        -   *Switch*.* library*.* switchname*  
  
    -   **작업 기반 비동기 패턴 (TAP) 변경**  
  
         대상으로 하는 응용 프로그램에는 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], <xref:System.Threading.Tasks.Task> 및 <xref:System.Threading.Tasks.Task%601> 개체 문화권 및 호출 스레드의 UI 문화권을 상속 합니다. 이전 버전의 .NET Framework를 대상으로 하거나 특정 버전의 .NET Framework를 대상으로 하지 않는 앱의 동작은 영향을 받지 않습니다. 자세한 내용은 "문화권 및 작업 기반 비동기 작업" 섹션을 참조는 <xref:System.Globalization.CultureInfo> 클래스 항목입니다.  
  
         <xref:System.Threading.AsyncLocal%601?displayProperty=fullName> 클래스를 사용 하는 같은 지정 된 비동기 제어 흐름에 로컬인 앰비언트 데이터를 나타낼 수는 `async` 메서드. 스레드 간에 데이터를 유지하는 데 사용할 수 있습니다. 앰비언트 데이터 변경 때문에 때마다 알립니다는 콜백 메서드를 정의할 수도 있습니다는 <xref:System.Threading.AsyncLocal%601.Value%2A?displayProperty=fullName> 명시적으로 변경 된 속성 또는 스레드 컨텍스트 전환이 발생 합니다.  
  
         세 가지 편의 메서드 <xref:System.Threading.Tasks.Task.CompletedTask%2A?displayProperty=fullName>, <xref:System.Threading.Tasks.Task.FromCanceled%2A?displayProperty=fullName>, 및 <xref:System.Threading.Tasks.Task.FromException%2A?displayProperty=fullName>, 작업 기반 비동기 패턴 (TAP)는 특정 상태에서 완료 된 작업을 반환 하에 추가 되었습니다.  
  
         <xref:System.IO.Pipes.NamedPipeClientStream> 클래스는 이제 새로운와 비동기 통신을 지원 <xref:System.IO.Pipes.NamedPipeClientStream.ConnectAsync%2A>합니다. 메서드를 재정의합니다.  
  
    -   **EventSource는 이벤트 로그에 쓰기를 지원**  
  
         이제 사용할 수는 <xref:System.Diagnostics.Tracing.EventSource> 클래스 관리 또는 운영 로그에 메시지를 이벤트 로그 뿐만 아니라 컴퓨터에서 만든 모든 기존 ETW 세션에 있습니다. 과거에는 이 기능을 위해 Microsoft.Diagnostics.Tracing.EventSource NuGet 패키지를 사용해야 했습니다. 이제 이 기능이 .NET Framework 4.6에 기본 제공됩니다.  
  
         NuGet 패키지 및 .NET Framework 4.6이 다음 기능으로 업데이트되었습니다.  
  
        -   **동적 이벤트**  
  
             이벤트 메서드를 만들지 않고 "즉시" 정의된 이벤트를 허용합니다.  
  
        -   **풍부한 페이로드**  
  
             기본 형식뿐만 아니라 특별하게 특성이 정의된 클래스 및 배열이 페이로드로 전달될 수 있도록 허용합니다.  
  
        -   **활동 추적**  
  
             시작과 중지 이벤트에서 현재 활성 중인 모든 작업을 나타내는 ID를 사용하여 이러한 이벤트 사이에서 발생하는 이벤트에 태그를 지정하도록 합니다.  
  
         이 지원 하기 위해 기능을 오버 로드 된 <xref:System.Diagnostics.Tracing.EventSource.Write%2A> 에 추가 된 메서드는 <xref:System.Diagnostics.Tracing.EventSource> 클래스입니다.  
  
-   **Windows Presentation Foundation (WPF)**  
  
    -   **HDPI 개선 사항**  
  
         이제 WPF의 HDPI 지원이 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]에서 보다 향상되었습니다. 테두리가 있는 컨트롤에 클리핑 인스턴스를 줄이기 위해 레이아웃 반올림을 변경했습니다. 이 기능은 경우에 기본적으로 사용 하면 <xref:System.Runtime.Versioning.TargetFrameworkAttribute> .NET 4.6로 설정 됩니다.  이전 버전의 framework 대상으로 하지만 실행 되는 응용 프로그램의 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 에 다음 줄을 추가 하 여 새로운 동작을 선택할 수는 [ <> \> ](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) app.config 파일의 섹션:  
  
        ```  
  
        <AppContextSwitchOverrides  
        value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false"  
        />  
  
        ```  
  
         이제 서로 다른 DPI 설정(다중 DPI 설치)을 사용하여 여러 대의 모니터에 걸쳐 있는 WPF 창이 블랙아웃 영역 없이 완전하게 렌더링됩니다. 이 새로운 동작을 사용하지 않으려면 app.config 파일의 `<appSettings>` 섹션에 다음 줄을 추가하여 옵트아웃(opt out)할 수 있습니다.  
  
        ```  
  
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>  
  
        ```  
  
         에 추가 된 DPI 설정에 따라 오른쪽 커서를 자동으로 로드에 대 한 지원이 <xref:System.Windows.Input.Cursor?displayProperty=fullName>합니다.  
  
    -   **터치는 것이 좋습니다.**  
  
         이 예제에서 고객 [연결](https://connect.microsoft.com/VisualStudio/feedback/details/903760/) 에서 해결 되었습니다 예기치 않은 동작이 생성 하는 터치는 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]합니다. 이제 Windows 스토어 응용 프로그램 및 WPF 응용 프로그램에 대한 두 번 탭하기 임계값이 Windows 8.1 이상 버전에서 같습니다.  
  
    -   **투명 한 자식 창 지원**  
  
         [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]의 WPF는 Windows 8.1 이상 버전에서 투명한 자식 창을 지원합니다. 이를 통해 최상위 창에서 사각형이 아닌 투명한 자식 창을 만들 수 있습니다. 설정 하 여이 기능을 사용할 수는 <xref:System.Windows.Interop.HwndSourceParameters.UsesPerPixelTransparency%2A?displayProperty=fullName> 속성을 `true`합니다.  
  
-   **Windows Communication Foundation (WCF)**  
  
    -   **SSL 지원**  
  
         이제 WCF가 전송 보안 및 클라이언트 인증으로 NetTcp를 사용할 때 SSL 3.0 및 TLS 1.0뿐만 아니라 SSL 버전 TLS 1.1 및 TLS 1.2를 지원합니다. 이제 사용할 프로토콜을 선택하거나 이전의 안정성이 낮은 프로토콜을 사용하지 않도록 설정할 수 있습니다. 이렇게 설정 하거나는 <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A> 속성 또는 구성 파일에 다음을 추가 하 여 합니다.  
  
        ```  
        <netTcpBinding>  
           <binding>  
              <security mode= "None|Transport|Message|TransportWithMessageCredential" >  
                 <transport clientCredentialType="None|Windows|Certificate"  
                            protectionLevel="None|Sign|EncryptAndSign"  
                            sslProtocols="Ssl3|Tls1|Tls11|Tls12">  
                    </transport>  
              </security>  
           </binding>  
        </netTcpBinding>  
  
        ```  
  
    -   **다양 한 HTTP 연결을 사용 하 여 메시지 보내기**  
  
         이제 WCF를 사용하여 사용자가 특정 메시지를 다른 기본 HTTP 연결을 사용하여 보낼 수 있습니다. 여기에는 두 가지 방법이 있습니다.  
  
        -   **연결 그룹 이름 접두사를 사용 하 여**  
  
             사용자가 WCF에서 연결 그룹 이름의 접두사로 사용할 문자열을 지정할 수 있습니다. 서로 다른 접두사를 가진 두 메시지는 서로 다른 기본 HTTP 연결을 사용하여 보내집니다. 접두사는 메시지에는 키/값 쌍을 추가 하 여 설정 <xref:System.ServiceModel.Channels.Message.Properties%2A?displayProperty=fullName> 속성입니다. 키가 "HttpTransportConnectionGroupNamePrefix"; 값은 원하는 접두사.  
  
        -   **다른 채널 팩터리를 사용 하 여**  
  
             사용자는 서로 다른 채널 팩터리로 만들어진 채널을 사용하여 보낸 메시지가 서로 다른 기본 HTTP 연결을 사용하도록 하는 기능을 사용하도록 설정할 수도 있습니다. 이 기능을 사용하려면 사용자가 다음 `appSetting`을 `true`로 설정해야 합니다.  
  
            ```  
  
            <appSettings>  
               <add key="wcf:httpTransportBinding:useUniqueConnectionPoolPerFactory" value="true" />  
            </appSettings>  
  
            ```  
  
-   **Windows Workflow Foundation WWF)**  
  
     이제 요청 시간이 초과되기 전에 처리 중인 "비 프로토콜" 책갈피가 있을 때 워크플로 서비스가 순서가 잘못된 작업 요청을 유지하는 시간을 초 단위로 지정할 수 있습니다. "비 프로토콜" 책갈피는 처리 중인 수신 작업에 관련되지 않은 책갈피입니다. 일부 작업은 구현되는 과정에서 비 프로토콜 책갈피를 만들기 때문에 비 프로토콜 책갈피가 있는지 정확히 알 수 없습니다. 여기에는 상태 및 선택이 포함됩니다. 따라서 워크플로 서비스를 상태 컴퓨터를 사용하여 구현하거나 선택 작업을 포함하여 구현한 경우 대부분 비 프로토콜 책갈피가 포함됩니다. app.config 파일의 `appSettings` 섹션에 다음과 같은 줄을 추가하여 간격을 지정합니다.  
  
    ```  
    <add key="microsoft:WorkflowServices:FilterResumeTimeoutInSeconds" value="60"/>  
    ```  
  
     기본값은 60초입니다. `value`가 0으로 설정되면 순서가 잘못된 요청은 다음과 같은 텍스트의 오류로 인해 즉시 거부됩니다.  
  
    ```Output  
    Operation 'Request3|{http://tempuri.org/}IService' on service instance with identifier '2b0667b6-09c8-4093-9d02-f6c67d534292' cannot be performed at this time. Please ensure that the operations are performed in the correct order and that the binding in use provides ordered delivery guarantees.   
    ```  
  
     순서가 잘못된 작업 메시지를 수신하고 비 프로토콜 책갈피가 없다면 동일한 메시지를 수신한 것입니다.  
  
     `FilterResumeTimeoutInSeconds` 요소의 값이&0;이 아니고 비 프로토콜 책갈피가 있으며 시간 제한 간격이 만료된 경우 시간 초과 메시지와 함께 작업이 실패합니다.  
  
-   **트랜잭션**  
  
     파생 된 예외가 발생 하 여 트랜잭션이 분산된 트랜잭션 식별자를 이제 포함할 수 있습니다 <xref:System.Transactions.TransactionException> throw 됩니다. 이렇게 하려면 app.config 파일의 `appSettings` 섹션에 다음 키를 추가합니다.  
  
    ```  
    <add key="Transactions:IncludeDistributedTransactionIdInExceptionMessage" value="true"/>   
    ```  
  
     기본값은 `false`입니다.  
  
-   **네트워킹**  
  
    -   **소켓 재사용**  
  
         Windows 10에는 새로운 확장성 높은 네트워킹 알고리즘이 있습니다. 이 알고리즘을 통해 아웃바운드 TCP 연결에 대한 로컬 포트를 재사용하여 컴퓨터 리소스를 효과적으로 사용할 수 있습니다. .NET Framework 4.6은 새 알고리즘을 지원하므로 .NET 앱이 새 동작을 활용할 수 있습니다. 이전 버전의 Windows에는 인위적인 동시 연결 제한(일반적으로 동적 포트 범위의 기본 크기는 16,384임)이 있었습니다. 이는 부하 상태에서 포트 소모를 발생시켜 서비스의 확장성을 제한할 수 있습니다.  
  
         [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]에는 두 개의 새 API가 추가되어 포트를 재사용할 수 있습니다. 이를 통해 동시 연결 시 64K 제한을 효과적으로 제거합니다.  
  
        -   <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName> 열거형 값입니다.  
  
        -   <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=fullName> 속성입니다.  
  
         기본적으로는 <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=fullName> 속성은 `false` 하지 않는 한는 `HWRPortReuseOnSocketBind` 의 값은 `HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319` 레지스트리 키가 0x1 설정 합니다. HTTP 연결에서 로컬 포트 재사용을 사용 하도록 설정 하려면 설정의 <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=fullName> 속성을 `true`합니다. 이 인해에서 나가는 모든 TCP 소켓 연결 <xref:System.Net.Http.HttpClient> 및 <xref:System.Net.HttpWebRequest> 새 Windows 10 소켓 옵션을 사용 하 여 [SO_REUSE_UNICASTPORT](https://msdn.microsoft.com/library/windows/desktop/ms740532.aspx), 로컬 포트를 재사용할 수 있게 하는 합니다.  
  
         소켓 전용 응용 프로그램을 작성 하는 개발자가 지정할 수는 <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName> 와 같은 메서드를 호출할 때 옵션 <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=fullName> 아웃 바운드 소켓 다시 바인딩하는 동안 로컬 포트를 사용할 수 있도록 합니다.  
  
    -   **국제 도메인 이름 및 PunyCode에 대 한 지원**  
  
         새 속성을 <xref:System.Uri.IdnHost%2A>를에 추가 되었습니다는 <xref:System.Uri> 국제 도메인 이름 및 PunyCode를 더 잘 지원 하기 위해 클래스입니다.  
  
-   **Windows Forms 컨트롤 크기 조정.**  
  
     이 기능은 확장 되었습니다 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 포함 하도록는 <xref:System.Windows.Forms.DomainUpDown>, <xref:System.Windows.Forms.NumericUpDown>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, <xref:System.Windows.Forms.DataGridViewColumn> 및 <xref:System.Windows.Forms.ToolStripSplitButton> 형식 및 지정 된 사각형은 <xref:System.Drawing.Design.PaintValueEventArgs.Bounds%2A> 속성 그릴 때 사용 되는 <xref:System.Drawing.Design.UITypeEditor>합니다.  
  
     이 기능은 옵트인(opt-in) 기능입니다. 이 기능을 사용하려면 아래와 같이 응용 프로그램 구성 파일(app.config)에서 `EnableWindowsFormsHighDpiAutoResizing` 요소를 `true`로 설정해야 합니다.  
  
    ```  
  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
  
    ```  
  
-   **코드 페이지 인코딩 지원**  
  
     [!INCLUDE[net_core](../../../includes/net-core-md.md)]에서는 주로 유니코드 인코딩을 지원하며, 기본적으로 코드 페이지 인코딩에 대한 제한된 지원을 제공합니다. 지원 되지 않는 하지만.NET Framework에서 사용할 수 있는 코드 페이지 인코딩에 대 한 지원을 추가할 수 있습니다 [!INCLUDE[net_core](../../../includes/net-core-md.md)] 코드 페이지 인코딩을 등록 하 여는 <xref:System.Text.Encoding.RegisterProvider%2A?displayProperty=fullName> 메서드. 자세한 내용은 참조 [System.Text.CodePagesEncodingProvider](https://msdn.microsoft.com/en-us/library/system.text.codepagesencodingprovider.aspx)합니다.  
  
-   **.NET 네이티브**  
  
     [!INCLUDE[net_core](../../../includes/net-core-md.md)]를 대상으로 하며 C# 또는 Visual Basic으로 작성된 Windows 10용 앱은 IL이 아니라 네이티브 코드로 앱을 컴파일하는 새 기술을 이용할 수 있습니다. 이렇게 생성된 앱은 시작 및 실행 시간이 훨씬 더 빠릅니다. 자세한 내용은 참조 [.NET 네이티브로 앱 컴파일](../../../docs/framework/net-native/index.md)합니다. JIT 컴파일 및 NGEN 둘 다에서 차이점 및 검사 하는.NET 네이티브의 개요에 대 한 코드에 대 한 참조 [.NET 네이티브 및 컴파일](../../../docs/framework/net-native/net-native-and-compilation.md)합니다.  
  
     Visual Studio 2015로 컴파일하는 경우 앱은 기본적으로 네이티브 코드로 컴파일됩니다. 자세한 내용은 참조 [.NET 네이티브 시작](../../../docs/framework/net-native/getting-started-with-net-native.md)합니다.  
  
     .NET 네이티브 앱 디버그를 지원하기 위해 다양한 인터페이스 및 열거형이 관리되지 않는 디버깅 API에 새로 추가되었습니다. 자세한 내용은 참조는 [디버깅 (관리 되지 않는 API 참조)](../../../ml/index.xml) 항목입니다.  
  
-   **오픈 소스.NET Framework 패키지**  
  
     [!INCLUDE[net_core](../../../includes/net-core-md.md)]변경 불가능 컬렉션을 같은 패키지 [SIMD Api](http://go.microsoft.com/fwlink/?LinkID=518639), 것과 같은 Api를 네트워크에서 발생 하 고는 <xref:System.Net.Http> 네임 스페이스에는 오픈 소스 패키지와 사용할 수 있습니다. [GitHub](https://github.com/)합니다. 코드에 액세스 하려면 참조 [GitHub의 NetFx](http://go.microsoft.com/fwlink/?LinkID=518634)합니다. 자세한 내용과 이러한 패키지에 기여 하는 방법에 대 한 참조 [.NET Core 및 오픈 소스](../../../docs/framework/get-started/net-core-and-open-source.md), [GitHub의.NET 홈페이지](http://go.microsoft.com/fwlink/?LinkID=518635)합니다.  
  
 [맨 위로 이동](#introduction)  
  
<a name="v452"></a>   
## <a name="whats-new-in-the-net-framework-452"></a>.NET Framework 4.5.2의 새로운 기능  
  
-   **ASP.NET 응용 프로그램에 대 한 새 Api입니다.** 새 <xref:System.Web.HttpResponse.AddOnSendingHeaders%2A?displayProperty=fullName> 및 <xref:System.Web.HttpResponseBase.AddOnSendingHeaders%2A?displayProperty=fullName> 메서드를 통해 검사 및 클라이언트 앱에 플러시되고 응답으로 응답 헤더 및 상태 코드를 수정할 수 있습니다. 대신 이러한 메서드를 사용 하는 것이 좋습니다.는 <xref:System.Web.HttpApplication.PreSendRequestHeaders> 및 <xref:System.Web.HttpApplication.PreSendRequestContent> 이벤트를 더 효율적이 고 신뢰할 수 있습니다.  
  
     <xref:System.Web.Hosting.HostingEnvironment.QueueBackgroundWorkItem%2A?displayProperty=fullName> 메서드를 사용 하면 소형 백그라운드 작업 항목을 예약할 수 있습니다. ASP.NET는 이러한 항목을 추적하여 모든 백그라운드 작업 항목이 완료될 때까지는 IIS가 작업자 프로세스를 갑자기 종료하지 못하도록 합니다. ASP.NET 관리되는 앱 도메인 외부에서는 이 메서드를 호출할 수 없습니다.  
  
     새 <xref:System.Web.HttpResponse.HeadersWritten?displayProperty=fullName> 및 <xref:System.Web.HttpResponseBase.HeadersWritten?displayProperty=fullName> 속성은 응답 헤더를 썼는지를 나타내는 부울 값을 반환 합니다. 수 이러한 속성을 사용 하면 확인을 호출 하는 Api와 같은 <xref:System.Web.HttpResponse.StatusCode%2A?displayProperty=fullName> (예외를 throw 헤더가 작성 된 경우)은 성공 합니다.  
  
-   **Windows Forms 컨트롤 크기 조정.** 이 기능은 확장되었습니다. 시스템 DPI 설정을 사용하여 다음과 같은 추가 컨트롤의 구성 요소 크기를 조정할 수 있습니다(예: 콤보 상자의 드롭다운 화살표).  
  
     <xref:System.Windows.Forms.ComboBox>   
     <xref:System.Windows.Forms.ToolStripComboBox>   
     <xref:System.Windows.Forms.ToolStripMenuItem>   
     <xref:System.Windows.Forms.Cursor>   
     <xref:System.Windows.Forms.DataGridView>   
     <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
     이 기능은 옵트인(opt-in) 기능입니다. 이 기능을 사용하려면 아래와 같이 응용 프로그램 구성 파일(app.config)에서 `EnableWindowsFormsHighDpiAutoResizing` 요소를 `true`로 설정해야 합니다.  
  
    ```  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
    ```  
  
-   **새 워크플로 기능입니다.** 사용 하는 리소스 관리자는 <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> 메서드 (구현 하는 <xref:System.Transactions.IPromotableSinglePhaseNotification> 인터페이스) 새 사용할 수 <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=fullName> 메서드는 다음을 요청할:  
  
    -   트랜잭션을 MSDTC(Microsoft Distributed Transaction Coordinator) 트랜잭션으로 승격합니다.  
  
    -   바꿉니다 <xref:System.Transactions.IPromotableSinglePhaseNotification> 와 <xref:System.Transactions.ISinglePhaseNotification>, 단일 단계 커밋이 지원 되는 지속적인 인 리스트 먼입니다.  
  
     이 기능은 동일한 앱 도메인 내에서 수행할 수 있으며 승격 수행을 위해 MSDTC와 상호 작용하기 위한 관리되지 않는 코드가 추가로 필요하지 않습니다. 처리 중인 호출이 하는 경우에 새 메서드를 호출할 수 있습니다 <xref:System.Transactions?displayProperty=fullName> 에 <xref:System.Transactions.IPromotableSinglePhaseNotification> `Promote` 승격 가능한 인리스트먼트에 의해 구현 되는 메서드.  
  
-   **프로 파일링 기능 향상.** 다음과 같은 관리되지 않는 새로운 프로파일링 API를 통해 더욱 강력한 프로파일링 기능이 제공됩니다.  
  
     [COR_PRF_ASSEMBLY_REFERENCE_INFO 구조](../../../ocs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)   
     [COR_PRF_HIGH_MONITOR 열거형](../../../ocs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)   
     [GetAssemblyReferences 메서드](../Topic/ICorProfilerCallback6::GetAssemblyReferences%20Method.md)   
     [GetEventMask2 메서드](../Topic/ICorProfilerInfo5::GetEventMask2%20Method.md)   
     [SetEventMask2 메서드](../Topic/ICorProfilerInfo5::SetEventMask2%20Method.md)   
     [AddAssemblyReference 메서드](../Topic/ICorProfilerAssemblyReferenceProvider::AddAssemblyReference%20Method.md)  
  
     이전 `ICorProfiler` 구현에서는 종속 어셈블리에 대한 지연 로딩이 지원되었습니다. 새로운 프로파일링 API의 경우 프로파일러에 의해 삽입된 종속 어셈블리는 앱이 완전히 초기화된 후에 로드되는 것이 아니라 즉시 로드할 수 있어야 합니다. 기존 `ICorProfiler` API 사용자에게는 이 변경 내용이 영향을 주지 않습니다.  
  
-   **디버깅 기능 향상.** 다음과 같은 관리되지 않는 새로운 디버깅 API를 통해 프로파일러와 더욱 완벽하게 통합할 수 있습니다. 덤프 디버깅 시 컴파일러 ReJIT 요청에 의해 생성된 로컬 변수 및 코드뿐 아니라 프로파일러가 삽입한 메타데이터를 액세스할 수 있습니다.  
  
     [SetWriteableMetadataUpdateMode 메서드](../Topic/ICorDebugProcess7::SetWriteableMetadataUpdateMode%20Method.md)   
     [EnumerateLocalVariablesEx 메서드](../Topic/ICorDebugILFrame4::EnumerateLocalVariablesEx%20Method.md)   
     [GetLocalVariableEx 메서드](../Topic/ICorDebugILFrame4::GetLocalVariableEx%20Method.md)   
     [GetCodeEx 메서드](../Topic/ICorDebugILFrame4::GetCodeEx%20Method.md)   
     [GetActiveReJitRequestILCode 메서드](../Topic/ICorDebugFunction3::GetActiveReJitRequestILCode%20Method.md)   
     [GetInstrumentedILMap 메서드](../Topic/ICorDebugILCode2::GetInstrumentedILMap%20Method.md)  
  
-   **이벤트 추적 변경 내용** .NET Framework 4.5.2에서는 대형 노출 영역에 대해 out-of-process로 실행되는 ETW(Windows용 이벤트 추적) 기반 작업 추적이 가능합니다. 이를 통해 APM(고급 전원 관리) 공급업체는 스레드 간의 각 요청 및 작업에 대한 비용을 정확하게 추적하는 간단한 도구를 제공할 수 있습니다.  이러한 이벤트는 ETW 컨트롤러에 의해 활성화된 경우에만 발생되므로 이전에 작성된 ETW 코드나 비활성화된 ETW로 실행된 코드에는 변경 내용이 적용되지 않습니다.  
  
-   **트랜잭션을 승격 하 고 영속적 참여 항목으로 변환**  
  
     <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=fullName> 는 새로운 API에 추가.NET Framework 4.5.2와 4.6:  
  
    ```  
  
    [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
    public Enlistment PromoteAndEnlistDurable(Guid resourceManagerIdentifier,  
                                              IPromotableSinglePhaseNotification promotableNotification,  
                                              ISinglePhaseNotification enlistmentNotification,  
                                              EnlistmentOptions enlistmentOptions)  
  
    ```  
  
     메서드는 인 리스트 먼 트 하 여 이전에 만든에서 사용할 수 <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=fullName> 에 대 한 응답은 <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=fullName> 메서드. 트랜잭션을 MSDTC 트랜잭션으로 승격하고 승격할 수 있는 인리스트먼트를 지속적인 인리스트먼트로 "변환"하도록 `System.Transactions`에게 요청합니다. 이 메서드가 성공적으로 완료 된 후의 <xref:System.Transactions.IPromotableSinglePhaseNotification> 인터페이스에서 더 이상 참조 되지 `System.Transactions`, 제공 된 이후 모든 알림이 도착 및 <xref:System.Transactions.ISinglePhaseNotification> 인터페이스입니다. 해당 인리스트먼트는 지속적인 인리스트먼트로 작동해야 하며 트랜잭션 로깅 및 복구를 지원합니다. 참조 <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=fullName> 대 한 자세한 내용은 합니다. 또한 인 리스트 먼 트를 지원 해야 <xref:System.Transactions.ISinglePhaseNotification>합니다.  이 메서드 수 *만* 처리 하는 동안 호출할 수는 <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=fullName> 를 호출 합니다. 경우 없는 경우는 <xref:System.Transactions.TransactionException> 예외가 throw 됩니다.  
  
 [맨 위로 이동](#introduction)  
  
<a name="v451"></a>   
## <a name="whats-new-in-the-net-framework-451"></a>.NET Framework 4.5.1의 새로운 기능  
 **2014 년 4 월 업데이트**:  
  
-   [Visual Studio 2013 업데이트 2](http://go.microsoft.com/fwlink/p/?LinkId=393658) 이러한 시나리오를 지원 하기 위해 이식 가능한 클래스 라이브러리 템플릿에 대 한 업데이트가 포함 되어 있습니다.  
  
    -   Windows 8.1, Windows Phone 8.1 및 Windows Phone Silverlight 8.1을 대상으로 하는 이식 가능한 라이브러리에서 Windows 런타임 API를 사용할 수 있습니다.  
  
    -   Windows 8.1 또는 Windows Phone 8.1을 대상으로 하는 경우 XAML(Windows.UI.XAML 형식)을 이식 가능한 라이브러리에 포함할 수 있습니다. XAML 템플릿(빈 페이지, 리소스 사전, 템플릿 컨트롤 및 사용자 정의 컨트롤)이 지원됩니다.  
  
    -   Windows 8.1 및 Windows Phone 8.1 대상의 스토어 앱에서 사용할 이식 가능한 Windows 런타임 구성 요소(.winmd 파일)를 만들 수 있습니다.  
  
    -   이식 가능한 클래스 라이브러리처럼 대상을 다시 Windows 스토어 또는 Windows Phone 스토어 클래스 라이브러리를 변경할 수 있습니다.  
  
     이러한 변경에 대 한 자세한 내용은 참조 [이식 가능한 클래스 라이브러리](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)합니다.  
  
-   이제 Windows 앱 빌드 및 배포를 위한 미리 컴파일 기술인 [!INCLUDE[net_native](../../../includes/net-native-md.md)]에 대한 설명서가 .NET Framework 콘텐츠 집합에 포함되었습니다. [!INCLUDE[net_native](../../../includes/net-native-md.md)]는 앱을 중간 언어가 아닌 네이티브 코드로 직접 컴파일하여 더 나은 성능을 제공합니다. 자세한 내용은 다음을 참조 하십시오. [.NET 네이티브로 앱 컴파일](../../../docs/framework/net-native/index.md)합니다.  
  
-   [.NET Framework 참조 소스](http://referencesource.microsoft.com/) 새로운 검색 환경과 향상 된 기능을 제공 합니다. 이제.NET Framework 소스 코드를 온라인으로 찾아볼 수 있습니다 [참조를 다운로드](http://referencesource.microsoft.com/download.html) 오프 라인으로 보기 및 디버그 시 소스 (패치 및 업데이트 포함)를 단계별로 실행 합니다. 자세한 내용은 블로그 항목을 참조 하십시오. [.NET 참조 소스에 대 한 새 모양을](http://blogs.msdn.com/b/dotnet/archive/2014/02/24/a-new-look-for-net-reference-source.aspx)합니다.  
  
 .NET Framework 4.5.1의 주요 새로운 기능 및 향상된 기능은 다음과 같습니다.  
  
-   어셈블리에 대한 자동 바인딩 리디렉션. [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)]부터는 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]을 대상으로 하는 응용 프로그램을 컴파일할 때 응용 프로그램 또는 해당 구성 요소가 동일한 어셈블리의 여러 버전을 참조할 경우 응용 프로그램 구성 파일에 바인딩 리디렉션을 추가할 수 있습니다. 또한 이전 버전의 .NET Framework를 대상으로 하는 프로젝트에 대해 이 기능을 사용하도록 설정할 수 있습니다. 자세한 내용은 참조 [하는 방법: 자동 바인딩 리디렉션 사용 안 함 및 사용](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)합니다.  
  
-   진단 정보를 수집하여 개발자가 서버 및 클라우드 응용 프로그램의 성능을 향상시키는 기능. 자세한 내용은 참조는 <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityId%2A> 및 <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore%2A> 의 메서드는 <xref:System.Diagnostics.Tracing.EventSource> 클래스입니다.  
  
-   가비지 수집 동안 LOH(대형 개체 힙)를 명시적으로 압축하는 기능. 자세한 내용은 참조는 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=fullName> 속성입니다.  
  
-   .NET Framework 업데이트를 통해 ASP.NET 응용 프로그램 일시 중단, 멀티 코어 JIT 개선 및 빠른 응용 프로그램 시작 등의 추가적인 성능 개선. 자세한 내용은 참조는 [.NET Framework 4.5.1 알림](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx) 및 [ASP.NET 앱 일시 중단](http://blogs.msdn.com/b/dotnet/archive/2013/10/09/asp-net-app-suspend-responsive-shared-net-web-hosting.aspx) 블로그 게시물입니다.  
  
 Windows Forms의 향상된 기능은 다음과 같습니다.  
  
-   Windows Forms 컨트롤 크기 조정. 앱의 응용 프로그램 구성 파일(app.config)의 항목을 선택하여 시스템 DPI 설정으로 컨트롤 구성 요소(예: 속성 표에 표시되는 아이콘)의 크기를 조정할 수 있습니다. 이 기능은 현재 다음과 같은 Windows Forms 컨트롤에서 지원됩니다.  
  
     <xref:System.Windows.Forms.PropertyGrid>   
     <xref:System.Windows.Forms.TreeView>   
     일부 측면은 <xref:System.Windows.Forms.DataGridView> (참조 [4.5.2의 새로운 기능](#v452) 지원 되는 추가 컨트롤에 대 한)  
  
     이 기능을 사용 하려면 새 추가 <> \> 구성 파일 (app.config)을 설정 하는 요소는 `EnableWindowsFormsHighDpiAutoResizing` 요소를 `true`:  
  
    ```  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
    ```  
  
 [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)]의 .NET Framework 응용 프로그램 디버깅 시 개선된 기능은 다음과 같습니다.  
  
-   Visual Studio 디버거에서 값 반환. [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)]에서 관리되는 응용 프로그램을 디버깅하면 자동 창에 메서드에 대한 반환 형식 및 값이 표시됩니다. 이 정보는 데스크톱, Windows 스토어 및 Windows Phone 응용 프로그램에서 사용할 수 있습니다. 자세한 내용은 참조 [메서드 호출의 반환 값 검사](http://msdn.microsoft.com/library/e3245b37-8e2e-4200-ba84-133726e95f1f\(v=vs.120\).aspx) MSDN Library에서.  
  
-   64비트 응용 프로그램의 편집하며 계속하기. [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)]은 데스크톱, Windows 스토어 및 Windows Phone용 64비트 관리되는 응용 프로그램의 편집하며 계속하기 기능을 지원합니다. 32 비트 및 64 비트 앱에 대 한 기존 제한은 계속 적용 (의 마지막 섹션을 참조는 [지원 되는 코드 변경 (C#)](http://msdn.microsoft.com/library/ms164927\(v=vs.120\).aspx) 문서).  
  
-   비동기 인식 디버깅. [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)]에서 비동기 응용 프로그램을 더 쉽게 디버깅하기 위해 호출 스택은 컴파일러에서 제공된 인프라 코드를 숨겨 비동기 프로그래밍을 지원하고, 논리 프로그램 실행을 보다 명확하게 반영할 수 있도록 논리 부모 프레임의 체인을 숨깁니다. 병렬 작업 창은 작업 창으로 대체되고 특정 중단점과 관련된 작업을 표시하며 응용 프로그램에서 현재 활성 상태이거나 예약된 다른 작업도 모두 표시합니다. "비동기 인식 디버깅" 섹션에서이 기능에 대해 읽을 수는 [.NET Framework 4.5.1 알림](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx)합니다.  
  
-   Windows 런타임 구성 요소에 대한 예외 지원 향상. [!INCLUDE[win81](../../../includes/win81-md.md)]에서는 다른 언어 간에도 예외의 원인인 오류에 대한 정보를 Windows 스토어 응용 프로그램에서 발생시킨 예외에 보존합니다. "Windows 스토어 앱 개발" 섹션에이 기능에 대해 읽을 수는 [.NET Framework 4.5.1 알림](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx)합니다.  
  
 부터는 [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], 사용할 수는 [관리 되는 프로필 기반 최적화 도구 (Mpgo.exe)](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md) 최적화 하기 위해 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 데스크톱 응용 프로그램 뿐 아니라 앱.  
  
 ASP.NET 4.5.1의에서 새로운 기능에 대 한 참조 [ASP.NET 4.5.1 및 Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) ASP.NET 사이트입니다.  
  
 [맨 위로 이동](#introduction)  
  
<a name="core"></a>   
## <a name="whats-new-in-the-net-framework-45"></a>.NET Framework 4.5의 새로운 기능  
  
### <a name="core-new-features-and-improvements"></a>주요 새로운 기능 및 향상된 기능  
  
-   배포 시 .NET Framework 4 응용 프로그램을 감지하고 닫아 시스템 다시 시작 횟수를 줄이는 기능. 참조 [시스템 다시 시작 줄이기.NET Framework 4.5 설치 하는 동안](../../../docs/framework/deployment/reducing-system-restarts.md)합니다.  
  
-   64비트 플랫폼에서 2GB보다 큰 배열 지원. 응용 프로그램 구성 파일에서 이 기능을 사용하도록 설정할 수 있습니다. 참조는 [ <> \> 요소](../../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md), 개체 크기와 배열 크기에 대 한 다른 제한도 나열 합니다.  
  
-   서버에 대한 백그라운드 가비지 수집을 통해 성능 향상. 사용자가 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서 서버 가비지 수집을 사용하면 백그라운드 가비지 수집을 사용하도록 자동으로 설정됩니다. 백그라운드 서버 가비지 수집 섹션을 참조는 [가비지 수집 기본 사항](../../../docs/standard/garbage-collection/fundamentals.md) 항목입니다.  
  
-   응용 프로그램 성능 개선을 위해 다중 코어 프로세서에서 선택적으로 사용 가능한 백그라운드 JIT(Just-In-Time) 컴파일. 참조 <xref:System.Runtime.ProfileOptimization>합니다.  
  
-   정규식 엔진이 시간 초과되기 전에 정규식 해결을 시도하는 시간을 제한하는 기능. 참조는 <xref:System.Text.RegularExpressions.Regex.MatchTimeout%2A?displayProperty=fullName> 속성입니다.  
  
-   응용 프로그램 도메인에 대한 기본 문화권을 정의하는 기능. 참조는 <xref:System.Globalization.CultureInfo> 클래스입니다.  
  
-   콘솔에서 유니코드(UTF-16) 인코딩 지원. 참조는 <xref:System.Console> 클래스입니다.  
  
-   문화권 문자열 순서 지정 및 비교 데이터의 버전 관리 지원. 참조는 <xref:System.Globalization.SortVersion> 클래스입니다.  
  
-   리소스 검색 시 성능 향상. 참조 [리소스 패키징 및 배포](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)합니다.  
  
-   압축 파일의 크기를 줄이기 위해 zip 압축 기능 개선. 참조는 <xref:System.IO.Compression?displayProperty=fullName> 네임 스페이스입니다.  
  
-   통해 기본 리플렉션 동작을 재정의 하도록 리플렉션 컨텍스트를 사용자 지정할 수는 <xref:System.Reflection.Context.CustomReflectionContext> 클래스입니다.  
  
-   다국어 도메인 이름에 응용 프로그램 IDNA ()의 2008 버전에 대 한 지원 표준 경우에는 <xref:System.Globalization.IdnMapping?displayProperty=fullName> 클래스에서 사용 됩니다 [!INCLUDE[win8](../../../includes/win8-md.md)]합니다.  
  
-   .NET Framework가 [!INCLUDE[win8](../../../includes/win8-md.md)]에서 사용되면 유니코드 6.0을 구현하는 문자열 비교가 운영 체제에 위임됨. 다른 플랫폼에서 실행되는 경우 유니코드 5.x를 구현하는 자체 문자열 비교 데이터가 .NET Framework에 포함됩니다. 참조는 <xref:System.String> 클래스와의 설명 섹션의 <xref:System.Globalization.SortVersion> 클래스입니다.  
  
-   응용 프로그램 도메인 단위로 문자열에 대한 해시 코드를 계산하는 기능. See [<>\> Element](../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md).  
  
-   형식 사이 분할할 리플렉션을 지원 <xref:System.Type> 및 <xref:System.Reflection.TypeInfo> 클래스입니다. 참조 [Windows 스토어 앱 용.NET Framework의 리플렉션](../../../docs/framework/reflection-and-codedom/reflection-for-windows-store-apps.md)합니다.  
  
### <a name="managed-extensibility-framework-mef"></a>MEF(Managed Extensibility Framework)  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]의 MEF(Managed Extensibility Framework)는 다음과 같은 새로운 기능을 제공합니다.  
  
-   제네릭 형식 지원  
  
-   특성이 아닌 명명 규칙을 기반으로 파트를 만들 수 있는 규칙 기반 프로그래밍 모델  
  
-   다중 범위  
  
-   [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램을 만들 때 사용할 수 있는 MEF의 하위 집합. 이 하위 집합은 사용할 수는 [다운로드 가능한 패키지](http://go.microsoft.com/fwlink/?LinkId=256238) NuGet 갤러리에서. 패키지를 설치 하려면 Visual Studio에서 프로젝트를 열고, 선택 **NuGet 패키지 관리** 에서 **프로젝트** 메뉴 및 온라인으로 검색 된 `Microsoft.Composition` 패키지 합니다.  
  
 자세한 내용은 참조 [Framework MEF (Managed Extensibility)](../../../docs/framework/mef/index.md)합니다.  
  
### <a name="asynchronous-file-operations"></a>비동기 파일 작업  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서는 C# 및 Visual Basic 언어에 새로운 비동기 기능이 추가되었습니다. 이러한 기능은 비동기 작업을 수행하는 작업 기반 모델을 추가합니다. 이 새로운 모델을 사용하려면 I/O 클래스에서 비동기 메서드를 사용합니다. 참조 [비동기 파일 I/O](../../../docs/standard/io/비동기-파일-i-o.md)합니다.  
  
<a name="tools"></a>   
### <a name="tools"></a>도구  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서 리소스 파일 생성기(Resgen.exe)를 사용하면 .NET Framework 어셈블리에 포함된 .resources 파일에서 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램에 사용할 .resw 파일을 만들 수 있습니다. 자세한 내용은 참조 [Resgen.exe (리소스 파일 생성기)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)합니다.  
  
 관리되는 프로필 기반 최적화(Mpgo.exe)를 사용하면 네이티브 이미지 어셈블리를 최적화하여 응용 프로그램 시작 시간, 메모리 사용률(작업 집합 크기) 및 처리량을 개선할 수 있습니다. 명령줄 도구는 네이티브 이미지 응용 프로그램 어셈블리에 대한 프로필 데이터를 생성합니다. 참조 [Mpgo.exe (관리 되는 프로필 기반 최적화 도구)](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md)합니다. [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)]부터는 Mpgo.exe를 사용하여 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램과 데스크톱 응용 프로그램을 최적화할 수 있습니다.  
  
<a name="parallel"></a>   
### <a name="parallel-computing"></a>병렬 컴퓨팅  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]는 병렬 컴퓨팅을 위한 몇 가지 새로운 기능과 향상된 기능을 제공합니다. 여기에는 성능 향상, 제어 강화, 비동기 프로그래밍에 대한 지원 개선, 새 데이터 흐름 라이브러리 및 병렬 디버깅 및 성능 분석에 대한 지원 개선이 포함됩니다. 항목을 참조 [.NET 4.5에서에서 병렬 처리에 대 한 새로운](http://go.microsoft.com/fwlink/?LinkId=235061) .NET 블로그를 사용한 병렬 프로그래밍에 있습니다.  
  
<a name="web"></a>   
### <a name="web"></a>웹  
 ASP.NET 4.5 및 4.5.1은 Web Forms, WebSocket 지원, 비동기 처리기, 성능 향상 및 기타 많은 기능을 바인딩하는 모델을 추가합니다. 자세한 내용은 다음 리소스를 참조하세요.  
  
-   [ASP.NET 4.5 및 Visual Studio 2012](../Topic/ASP.NET%20Core%20and%20Visual%20Studio%202015.md) MSDN Library에서.  
  
-   [ASP.NET 4.5.1 및 Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) ASP.NET 사이트입니다.  
  
<a name="networking"></a>   
### <a name="networking"></a>네트워킹  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서는 HTTP 응용 프로그램의 새로운 프로그래밍 인터페이스를 제공합니다. 자세한 내용은 참조 새 <xref:System.Net.Http?displayProperty=fullName> 및 <xref:System.Net.Http.Headers?displayProperty=fullName> 네임 스페이스입니다.  
  
 지원도 허용 하 고 기존를 사용 하 여 WebSocket 연결와의 상호 작용 하는 새로운 프로그래밍 인터페이스에 대 한 포함 되어 <xref:System.Net.HttpListener> 및 관련 클래스입니다. 자세한 내용은 참조 새 <xref:System.Net.WebSockets> 네임 스페이스 및 <xref:System.Net.HttpListener> 클래스입니다.  
  
 또한 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에는 다음 네트워킹 개선 사항이 포함되어 있습니다.  
  
-   RFC 규격 URI 지원. 자세한 내용은 참조 <xref:System.Uri> 및 관련 클래스입니다.  
  
-   IDN(Internationalized Domain Name) 구문 분석 지원. 자세한 내용은 참조 <xref:System.Uri> 및 관련 클래스입니다.  
  
-   EAI(Email Address Internationalization) 지원. 자세한 내용은 참조는 <xref:System.Net.Mail> 네임 스페이스입니다.  
  
-   IPv6 지원 개선. 자세한 내용은 참조는 <xref:System.Net.NetworkInformation> 네임 스페이스입니다.  
  
-   이중 모드 소켓 지원. 자세한 내용은 참조는 <xref:System.Net.Sockets.Socket> 및 <xref:System.Net.Sockets.TcpListener> 클래스입니다.  
  
<a name="client"></a>   
### <a name="windows-presentation-foundation-wpf"></a>WPF(Windows Presentation Foundation)  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]의 WPF(Windows Presentation Foundation)에서 변경되고 개선된 영역은 다음과 같습니다.  
  
-   새 <xref:System.Windows.Controls.Ribbon.Ribbon> 빠른 실행 도구 모음, 응용 프로그램 메뉴 및 탭을 호스팅하는 리본 사용자 인터페이스를 구현할 수 있는 컨트롤입니다.  
  
-   새 <xref:System.ComponentModel.INotifyDataErrorInfo> 인터페이스는 동기 및 비동기 데이터 유효성 검사를 지원 합니다.  
  
-   새로운 기능에 대 한는 <xref:System.Windows.Controls.VirtualizingPanel> 및 <xref:System.Windows.Threading.Dispatcher> 클래스입니다.  
  
-   그룹화된 큰 데이터 집합을 표시하고 UI가 아닌 스레드에서 컬렉션에 액세스할 때의 성능 개선  
  
-   정적 속성에 데이터를 구현 하는 형식은 데이터 바인딩 사용자 지정으로 <xref:System.Reflection.ICustomTypeProvider> 인터페이스 및 바인딩 식에서 데이터 바인딩 정보 검색 합니다.  
  
-   값이 변경될 때(라이브 셰이핑) 데이터의 위치 변경  
  
-   항목 컨테이너에 대한 데이터 컨텍스트 연결을 해제할지 여부를 확인하는 기능  
  
-   속성 변경과 데이터 소스 업데이트 간에 경과되어야 하는 시간을 설정하는 기능  
  
-   취약한 이벤트 패턴을 구현하기 위한 지원 개선. 또한 이벤트가 태그 확장을 수락할 수 있습니다.  
  
<a name="windows_communication_foundation"></a>   
### <a name="windows-communication-foundation-wcf"></a>WCF(Windows Communication Foundation)  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서 WCF(Windows Communication Foundation) 응용 프로그램을 더 쉽게 작성하고 유지 관리할 수 있도록 다음 기능이 추가되었습니다.  
  
-   생성된 구성 파일의 단순화  
  
-   계약 중심 개발 지원  
  
-   ASP.NET 호환성 모드를 더 쉽게 구성하는 기능  
  
-   기본 전송 속성 값을 변경하여 값을 설정해야 할 가능성을 줄임  
  
-   업데이트는 <xref:System.Xml.XmlDictionaryReaderQuotas> 줄이려면 XML 사전 판독기에 대 한 할당량을 수동으로 구성 해야 하는 클래스입니다.  
  
-   Visual Studio에서 빌드 프로세스의 일부로 WCF 구성 파일의 유효성 검사를 실시하여 응용 프로그램 실행 전에 구성 오류를 검색할 수 있도록 함  
  
-   새로운 비동기 스트리밍 지원  
  
-   새 HTTPS 프로토콜 매핑을 사용하면 간단하게 IIS(인터넷 정보 서비스)로 HTTPS에서 끝점을 표시할 수 있음  
  
-   서비스 URL에 `?singleWSDL`을 추가하여 단일 WSDL 문서에서 메타데이터를 생성하는 기능  
  
-   Websocket이 포트 80 및 443에서 완벽한 양방향 통신을 지원하며 성능 특성은 TCP 전송과 유사함  
  
-   코드에서 서비스 구성 지원  
  
-   XML 편집기 도구 설명  
  
-   <xref:System.ServiceModel.ChannelFactory> 캐싱 지원 합니다.  
  
-   이진 인코더 압축 지원  
  
-   개발자가 "실행 후 제거" 메시징을 사용하는 서비스를 작성할 수 있는 UDP 전송 지원. 클라이언트는 서비스에 메시지를 보내고 서비스에서 응답을 기대하지 않습니다.  
  
-   HTTP 전송 및 전송 보안 사용 시 단일 WCF 끝점에 대한 여러 인증 모드를 지원하는 기능  
  
-   IDN(Internationalized Domain Name)을 사용하는 WCF 서비스 지원  
  
 자세한 내용은 참조 [Windows Communication Foundation의 새로운](http://go.microsoft.com/fwlink/?LinkId=228173)합니다.  
  
<a name="windows_workflow_foundation"></a>   
### <a name="windows-workflow-foundation-wf"></a>Windows WF(Workflow Foundation)  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]의 Windows WF(Workflow Foundation)에 몇 가지 새로운 기능이 추가되었습니다.  
  
-   상태 시스템 워크플로가.NET Framework 4.0.1의 일부로 처음 도입 되었습니다 ([.NET Framework 4 플랫폼 업데이트 1](http://go.microsoft.com/fwlink/?LinkID=215092)). 이 업데이트에는 개발자가 상태 시스템 워크플로를 만들 수 있도록 하는 몇 가지 새로운 클래스와 활동이 포함되었습니다. 이러한 클래스와 활동은 다음을 포함하도록 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에 대해 업데이트되었습니다.  
  
    -   상태에 중단점을 설정하는 기능  
  
    -   Workflow Designer에서 전환을 복사하여 붙여 넣는 기능  
  
    -   공유 트리거 전환 작성을 위한 디자이너 지원  
  
    -   포함 하 여 상태 시스템 워크플로 만들기 위한 활동: <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State>, 및 <xref:System.Activities.Statements.Transition>합니다.  
  
-   다음과 같은 향상된 Workflow Designer 기능  
  
    -   향상 된 Visual Studio에서 워크플로 검색 기능 등 **빠른 찾기** 및 **파일에서 찾기**합니다.  
  
    -   컨테이너 활동에 두 번째 자식 활동이 추가될 때 Sequence 활동을 자동으로 생성하고 두 활동 모두를 Sequence 활동에 포함하는 기능  
  
    -   스크롤 막대를 사용하지 않고 워크플로의 보이는 부분을 변경할 수 있는 이동 기능 지원  
  
    -   새 **문서 개요** 의 구성 요소를 선택 하는 뷰를 트리 스타일 개요 뷰에서 워크플로의 구성 요소를 표시 하 고 있습니다는 **문서 개요** 보기.  
  
    -   활동에 주석을 추가하는 기능  
  
    -   Workflow Designer를 사용하여 활동 대리자를 정의하고 사용하는 기능  
  
    -   상태 시스템과 순서도 워크플로에서 활동 및 전환의 자동 연결 및 자동 삽입  
  
-   XAML 파일의 단일 요소에 워크플로의 뷰 상태 정보가 저장되므로 뷰 상태 정보를 쉽게 찾아 편집할 수 있음  
  
-   자식 활동이 지속되지 않도록 하는 NoPersistScope 컨테이너 활동  
  
-   C# 식에 대한 지원  
  
    -   Visual Basic을 사용하는 워크플로 프로젝트에서는 Visual Basic 식을 사용하고, C# 워크플로 프로젝트에서는 C# 식을 사용합니다.  
  
    -   Visual Studio 2010에서 만들어지고 Visual Basic 식이 있는 C# 워크플로 프로젝트는 C# 식을 사용하는 C# 워크플로 프로젝트와 호환됩니다.  
  
-   버전 관리 향상  
  
    -   새 <xref:System.Activities.WorkflowIdentity> 지속형된 워크플로 인스턴스와 해당 워크플로 정의 간의 매핑을 제공 하는 클래스입니다.  
  
    -   포함 하 여 같은 호스트에서 여러 워크플로 버전의 side-by-side-실행 <xref:System.ServiceModel.Activities.WorkflowServiceHost>합니다.  
  
    -   동적 업데이트에서 지속된 워크플로 인스턴스의 정의를 수정할 수 있는 기능  
  
-   기존 서비스 계약과 일치하도록 자동 생성 활동에 대한 지원을 제공하는 계약 중심 워크플로 서비스 개발  
  
 자세한 내용은 참조 [Windows Workflow Foundation의 새로운](http://go.microsoft.com/fwlink/?LinkId=228176)합니다.  
  
<a name="tailored"></a>   
### [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]  
 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램은 특정 폼 팩터용으로 설계되었으며 Windows 운영 체제의 강력한 기능을 활용합니다. [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 또는 4.5.1의 하위 집합은 C# 또는 Visual Basic을 사용하여 Windows용 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램을 빌드하는 데 사용할 수 있습니다. 이 하위 집합 이라고 [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] 에 설명 되어 있는 [개요](http://go.microsoft.com/fwlink/?LinkId=228491) Windows 개발자 센터의입니다.  
  
<a name="portable"></a>   
### <a name="portable-class-libraries"></a>이식 가능한 클래스 라이브러리  
 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)] 및 이후 버전의 이식 가능한 클래스 라이브러리 프로젝트를 사용하여 여러 .NET Framework 플랫폼에서 작동하는 관리되는 어셈블리를 작성하고 빌드할 수 있습니다. 이식 가능한 클래스 라이브러리 프로젝트를 사용하여 대상 플랫폼(예: Windows Phone 및 [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)])을 선택합니다. 프로젝트에서 사용할 수 있는 형식 및 멤버는 이러한 플랫폼에서 공용 형식 및 멤버로 자동으로 제한됩니다. 자세한 내용은 참조 [이식 가능한 클래스 라이브러리](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [.NET Framework 및 번 외 릴리스](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)   
 [Visual Studio 2013의 새로운 기능](http://msdn.microsoft.com/library/bb386063\(v=vs.120\).aspx)   
 [ASP.NET 4.5.1 및 Visual Studio 2013 용 웹 도구](http://go.microsoft.com/fwlink/?LinkID=309094)   
 [ASP.NET 및 웹용 Visual Studio](../Topic/ASP.NET%20and%20Visual%20Studio%20for%20Web.md)   
 [Windows Communication Foundation의 새로운 기능](http://go.microsoft.com/fwlink/?LinkId=228173)   
 [Windows Workflow Foundation의 새로운 기능](http://go.microsoft.com/fwlink/?LinkId=228176)   
 [Visual c + +의 새로운 기능](http://msdn.microsoft.com/library/hh409293\(v=vs.120\).aspx)