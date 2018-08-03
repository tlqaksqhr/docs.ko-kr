---
title: '&lt;AppContextSwitchOverrides&gt; 요소'
ms.custom: updateeachrelease
ms.date: 04/19/2018
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d16ce7f2744869c812b9988e91edd153d9cb4fd2
ms.sourcegitcommit: e8dc507cfdaad504fc9d4c83d28d24569dcef91c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2018
ms.locfileid: "32747527"
---
# <a name="ltappcontextswitchoverridesgt-element"></a>&lt;AppContextSwitchOverrides&gt; 요소
<xref:System.AppContext> 클래스에 사용되는 스위치를 하나 이상 정의하여 새 기능의 옵트아웃 메커니즘을 제공합니다.  
  
 \<configuration>  
 \<runtime>  
\<AppContextSwitchOverrides>  
  
## <a name="syntax"></a>구문  
  
```xml  
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`value`|필수 특성입니다.<br /><br /> 하나 이상의 스위치 이름 및 연결 된 부울 값을 정의합니다.|  
  
### <a name="value-attribute"></a>특성 값  
  
|값|설명|  
|-----------|-----------------|  
|"name=value"|해당 값과 함께 하는 미리 정의 된 스위치 이름 (`true` 또는 `false`). 여러 스위치 이름/값 쌍은 세미콜론으로 구분 됩니다 (";"). 에서.NET Framework에서 지원 되는 미리 정의 된 스위치 이름 목록은 설명 섹션을 참조 하세요.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework 4.6 부터는 `<AppContextSwitchOverrides>` 앱 새 기능을 활용할 수 있습니다 또는 라이브러리의 이전 버전과 호환성을 유지 하는지 여부를 결정 하기 위한 API의 호출자를 허용 하는 구성 파일의 요소입니다. 예를 들어 API의 동작 라이브러리의 두 버전 간의 변경 된 경우는 `<AppContextSwitchOverrides>` 요소 라이브러리의 새 기능을 지 원하는 버전에 대 한 새 동작을 옵트아웃 하려면 해당 API의 호출자를 허용 합니다. .NET Framework에서 Api를 호출 하는 앱을 `<AppContextSwitchOverrides>` 요소 호출자가 해당 앱 대상를 포함 하는.NET Framework의 버전에서 해당 앱이 실행 되는 경우 새 기능을 옵트인 하려면.NET Framework의 이전 버전을 허용할 수도 있습니다 기능입니다.  
  
 합니다 `value` 특성을 `<AppContextSwitchOverrides>` 요소 하나 이상의 세미콜론으로 구분 된 이름/값 쌍으로 이루어진 단일 문자열로 구성 됩니다.  호환성 스위치를 식별 하는 각 이름 및 해당 값은 부울 (`true` 또는 `false`) 스위치가 설정 되었는지 여부를 나타내는입니다. 스위치는 기본적으로 `false`, 라이브러리의 새로운 기능을 제공 합니다. 제공 하므로 이전 기능 스위치가 설정 된 경우 (즉, 해당 값은 `true`). 이렇게 하면 라이브러리의 새로운 기능을 옵트아웃 하려면 이전 동작에 의존 하는 호출자를 허용 하는 동안 기존 API에 대 한 새 동작을 제공할 수 있습니다.  
  
 .NET Framework에서는 다음 스위치를 지원합니다.  
  
|스위치 이름|설명|도입|  
|-----------------|-----------------|----------------|  
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Windows Presentation Foundation 컨트롤 레이아웃에 대 한 레거시 알고리즘을 사용 하는지 여부를 제어 합니다. 자세한 내용은 [완화: WPF 레이아웃](~/docs/framework/migration-guide/mitigation-wpf-layout.md)을 참조하십시오.|.NET Framework 4.6|  
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|한 PackageDigitalSignatureManager 서명 패키지 부분에 사용 되는 기본 알고리즘은 SHA1 또는 SHA256 여부를 제어 합니다.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|로 설정 하면 `false`, FIPS가 활성화 하는 경우 Visual Studio를 사용 하 여 XAML 기반 워크플로 프로젝트를 디버깅할 수 있습니다. 없으면를 <xref:System.NullReferenceException> System.Activities 어셈블리의 메서드 호출에서 throw 됩니다.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|디버거에서 워크플로 인스턴스에 대 한 체크섬 MD5 또는 SHA1 사용 하는지 여부를 제어 합니다. | .NET Framework 4.7|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|원본 파일 및 줄 정보를 포함할 수 이식 가능한 Pdb를 사용 하는 경우 스택 추적 가져오기 하는 여부를 제어 합니다. `false` 소스 파일 및 줄 정보를 포함 하려면 그렇지 않으면 `true`합니다.|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|컨트롤 여부를 <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> 메서드에서 예외를 throw 때는 <xref:System.Drawing.Icon> 개체에 PNG 프레임이 있는 합니다. 자세한 내용은 [완화: 아이콘 개체의 PNG 프레임](~/docs/framework/migration-guide/mitigation-png-frames-in-icon-objects.md)을 참조하십시오.|.NET Framework 4.6|  
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|결정 여부 <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> 사용 하 여 컬렉션에 추가 될 때 개체가 제대로 삭제 됩니다는 <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType> 메서드. `true` 레거시 동작을 유지 하려면 `false` 모든 개인 글꼴 개체의 삭제 합니다. |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`</br>`OptimizePrintPreview`|컨트롤 여부를 성능을 <xref:System.Windows.Forms.PrintPreviewDialog> 네트워크 프린터에 대해 최적화 됩니다. 자세한 내용은 [PrintPreviewDialog 컨트롤 개요](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md)합니다.|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|비동기 작업 호출 스레드의 컨텍스트에서 이동 하지 않는 있는지 여부를 제어 합니다. 자세한 내용은 [CurrentCulture 및 CurrentUICulture가 작업에 걸쳐 전달](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks)합니다.|.NET Framework 4.6|  
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|컨트롤 여부는 <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> 메서드를 마지막 DNS 항목에만 클레임 유형과 일치 하도록 시도 합니다. 자세한 내용은 [완화: X509CertificateClaimSet.FindClaims 메서드](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md)를 참조하십시오.|.NET Framework 4.6.1|  
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|AuthorizationContext.Empty 변경할 수 있는 개체를 반환할 수 있도록 할지 여부를 제어 합니다.|.NET Framework 4.6|  
|`Switch.System.IO.BlockLongPaths`|컨트롤 여부를 보다 긴 경로 `MAX_PATH` (260 자)를 throw 한 <xref:System.IO.PathTooLongException>합니다. 자세한 내용은 [긴 경로 지원](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support)합니다.|.NET Framework 4.6.2|  
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|압축 풀기에 네이티브 OS 루틴을 사용할지 여부를 제어 합니다 <xref:System.IO.Compression.DeflateStream> 클래스입니다. `false` 네이티브 Api를 사용 하려면 `true` 사용 하 여 <xref:System.IO.Compression.DeflateStream> 구현 합니다.|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|백슬래시를 사용 하 여 ("\\") 대신 슬래시 ("/")에서 경로 구분 기호로 <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> 속성입니다. 자세한 내용은 [완화: ZipArchiveEntry.FullName 경로 구분 기호](~/docs/framework/migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md)합니다.|.NET Framework 4.6.1|  
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|사용 하 여 만든 백그라운드 스레드에서 throw 되는 시스템 예외를 운영 하 고 있는지 여부를 제어 <xref:System.IO.Ports.SerialPort> 스트림을 프로세스를 종료 합니다.|.NET Framework 4.7.1| 
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|레거시 경로 정규화 사용 되 고 URI 경로 지 여부를 제어 합니다 <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> 고 <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> 메서드. 자세한 내용은 [완화: 경로 정규화](~/docs/framework/migration-guide/mitigation-path-normalization.md) 하 고 [완화: 경로 콜론 검사](~/docs/framework/migration-guide/mitigation-path-colon-checks.md)합니다.|.NET Framework 4.6.2|  
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|같음 비교에 대 한 테스트가 있는지 여부를 제어 합니다 <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> 개체의 속성을 <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> 두 번째 개체의 속성입니다. 자세한 내용은 [MemberDescriptor.Equals의 잘못 된 구현](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals)합니다.|.NET Framework 4.6.2|  
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|사용 하지 않도록 설정 된 키 사용 (EKU) 개체 식별자 (OID) 유효성 검사를 인증서입니다. EKU(향상된 키 사용) 확장은 키를 사용하는 응용 프로그램을 나타내는 OID(개체 식별자)의 모음입니다.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|SCH_SEND_AUX_RECORD 사용을 사용 하지 않도록 설정 하 여 완화 방법은 TLS1.0 브라우저 악용에 대해 SSL/TLS (비스 트)를 사용 하지 않도록 설정 합니다.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|컨트롤 여부는 <xref:System.Net.ServicePointManager?displayProperty=nameWithType> 및 <xref:System.Net.Security.SslStream?displayProperty=nameWithType> 클래스는 SSL 3.0 프로토콜을 사용할 수 있습니다. 자세한 내용은 [완화: TLS 프로토콜](~/docs/framework/migration-guide/mitigation-tls-protocols.md)을 참조하십시오.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Tls11, Tls12, Tls 기본값으로 다시 되돌리기 SystemDefault TLS 버전을 사용 하지 않도록 설정 합니다.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|SslStream TLS 서버 쪽 경고를 사용 하지 않도록 설정 합니다.|.NET Framework 4.7|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |컨트롤 여부는 [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) ECMAScript V6 및 V8 표준에 따라 일부 제어 문자를 serialize 합니다. 자세한 내용은 [완화: DataContractJsonSerializer로 제어 문자 serialization](Mitigation:%20Serialization%20of%20Control%20Characters%20with%20the%20DataContractJsonSerializer.md)을 참조하세요.| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|컨트롤 여부는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 시간대에 대해 여러 조정 또는 하나의 조정만 지원 합니다. 경우 `true`를 사용 하 여 합니다 <xref:System.TimeZoneInfo> serialize 할 입력 날짜 및 시간 데이터를 deserialize 하 고 사용 하 여이 고, 그렇지는 <xref:System.TimeZone> 여러 조정 규칙을 지원 하지 않는 형식입니다.|.NET Framework 4.6.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|컨트롤 여부는 <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=nameWithType> 새 개체를 설정 하는 생성자 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> 기존 개체 참조를 사용 하 여 속성입니다. 자세한 내용은 [완화: ClaimsIdentity 생성자](~/docs/framework/migration-guide/mitigation-claimsidentity-constructor.md)를 참조하세요.|.NET Framework 4.6.2|  
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|컨트롤 여부를 다시 사용 하려고 합니다는 <xref:System.Security.Cryptography.AesCryptoServiceProvider> decryptor throw를 <xref:System.Security.Cryptography.CryptographicException>입니다. 자세한 내용은 [AesCryptoServiceProvider 암호 해독 기가 재사용 가능 변환을 제공](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform)합니다.|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|컨트롤 여부를 값을 [cspparameters.parentwindowhandle에](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) 속성은는 [IntPtr](xref:System.IntPtr) 나타내는 창에 메모리 위치 처리 또는 창 핸들 (HWND) 인지는. 자세한 내용은 [완화: CspParameters.ParentWindowHandle에 HWND 필요](Mitigation:%20CspParameters.ParentWindowHandle%20Expects%20an%20HWND.md)를 참조하세요. |.NET Framework 4.7|   
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|일부 SignedCMS 작업에 대 한 기본값은 SHA1 또는 SHA256 여부를 결정 합니다. |.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|일부 SignedXML 작업에 대 한 기본값은 SHA1 또는 SHA256 여부를 결정 합니다. |.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|결정 하는지 여부를 `TransportWithMessageCredential` 보안 모드에서는 메시지를 부호 없는 "to" 헤더가 합니다. 이 옵트인 스위치입니다. 자세한 내용은 [.NET Framework 4.6.1의에서 런타임 변경 내용](https://msdn.microsoft.com/library/mt592686.aspx#WCF)합니다.|.NET Framework 4.6.1| 
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|컨트롤 여부를 합니다 <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> 생성자에서 throw를 <xref:System.ArgumentException> 요소 중 하나 이면 `null`합니다.|.NET Framework 4.7.1| 
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|CSG 키 저장소 공급자를 예외를 throw X509를 사용 하려고 인증서를 사용 하 여 여부를 결정 합니다. 자세한 내용은 [WCF 전송 보안에서 CNG를 사용 하 여 저장 한 인증서 지원](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng)합니다.|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|자체 호스팅된 서비스에서 HTTP 전송을 사용 하는 경우이 값을 설정 `true` 를 추가 하는 응용 프로그램을 무시 하려면 wcf는 `Connection: close` 헤더는 요청에 대 한 응답 헤더를 합니다. 이 값을 설정 `false` 을 추가할 수는 `Connection: close` 헤더 응답 헤더를 응답을 보낸 후 요청 소켓 닫기의 결과입니다.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|재진입 서비스의 인스턴스는 단일 실행 스레드를 한 번에 제한에서 발생 하는 교착 상태를 처리 합니다.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|와 함께 `Switch.System.Net.DontEnableSchUseStrongCrypto`, WCF 메시지 보안에서 TLS 1.1 및 TLS 1.2를 사용 하는지를 결정 합니다.|.NET Framework 4.7 |    
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|값 `false` 에서 운영 체제가 프로토콜을 선택 하도록 허용 하는 기본 구성을 설정 합니다. 값 `true` 기본으로 사용할 수 있는 가장 높은 프로토콜을 설정 합니다. (에서도 다운로드 가능 서비스 이전 프레임 워크 버전의 분기)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|SHA1 또는 SHA256 서명 알고리즘 WCF에서 MSMQ 메시지에 대 한 기본 메시지 인지 확인 합니다.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|WCF는 SHA1 또는 SHA256 해시를 명명 된 파이프에 대 한 임의 이름을 생성을 사용 하는지 여부를 제어 합니다.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|발생시킬지 여부를 제어 하는 [NullReferenceException](xref:System.NullReferenceException) 예외 메시지가 null 인 경우.|.NET Framework 4.7|  
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|서비스 시작 시 throw 된 예외는 호출자에 게 전파 하는지 여부를 제어 합니다 <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> 메서드.|.NET Framework 4.7.1|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|때로는 디코딩되는 특정 백분율로 인코딩된 문자를 왼쪽 일관 되 게 인코딩할 이제는 지 여부를 결정 합니다. 하는 경우 `true`,이 고, 그렇지 않으면 디코딩된 `false`합니다.|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Uri에서 유니코드 양방향 문자를 처리를 결정합니다. `true` Uri;에서를 제거 하려면 `false` 유지 하 고 % 인코딩해야 합니다.|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Windows Presentation Foundation 이전 알고리즘을 적용 하는지 여부를 결정 (`true`) 또는 새 알고리즘 (`false`)에서 공간을 할당 \*-열입니다. 자세한 내용은 [완화: Grid 컨트롤의 별 열 공간 할당](Mitigation:%20Grid%20Control's%20Space%20Allocation%20to%20Star-columns.md)을 참조하세요. |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|컨트롤 선택 발생 하기 전에 선택한 값 속성의 값을 업데이트 여부 선택기 또는 탭 컨트롤에서 항상 변경 이벤트입니다.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|비 표시기 기반된 선택 렌더링에 사용할 수 있는 인지 여부를 확인 합니다 <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.PasswordBox> 폐색 텍스트를 방지 하기 위한 컨트롤 (`false`), 아니면 텍스트 표시기 계층에만 렌더링 됩니다 (`true`).|.NET Framework 4.7.2|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|DPI 변경 당 시스템에서 발생할 지 여부를 결정 (값 `false`) 또는 모니터별 (값 `true`).|.NET Framework 4.6.2|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|개발자를 특별히 처리 해야 하는지 여부를 결정 합니다 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 작업은 컨트롤 텍스트가 존재 하는 경우. `true` 처리 하는 <xref:System.Windows.Forms.DomainUpDown.UpButton> 작업; `false` 에 대 한는 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 고 <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> 제대로 동기화 되어야 하는 작업입니다.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|사용자 지정을 허용 하는 코드에서 옵트아웃 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 구현 안전 하 게 예외를 throw 하지 않고 메시지를 필터링 할 때를 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> 메서드가 호출 됩니다. 자세한 내용은 [완화: 사용자 지정 IMessageFilter.PreFilterMessage 구현](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)을 참조하십시오.|.NET Framework 4.6.1|  
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|결정 여부는 <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> 속성에서 중첩 된 메뉴를 열면 원본 제어를 반환 합니다 <xref:System.Windows.Forms.ToolStripMenuItem> 컨트롤입니다. `true` 반환할 `null`, 레거시 동작입니다. `false` 소스 제어를 반환 합니다.|.NET Framework 4.7.2|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|선택적인 지 여부를 결정 `WM_POINTER`-기반된 터치/스타일러스 스택 WPF 응용 프로그램에서 사용 가능 합니다. 자세한 내용은 참조 하세요. [완화: 포인터 기반 터치 및 스타일러스 지원](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md)|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|SHA256 체크섬에 사용 되는 기본 해시 알고리즘 인지 확인 (`false`) 또는 SHA1 (`true`).|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|레거시 있는지 여부를 제어 [NullReferenceException](xref:System.NullReferenceException) 대신 예외의 원인을 더 구체적으로 나타내는 예외가 throw 됩니다 (같은 [DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException) 또는 [ FileNotFoundException](xref:System.IO.FileNotFoundException)합니다. 처리에 의존 하는 코드에서 사용 하 여 위한 것은 [NullReferenceException](xref:System.NullReferenceException)합니다. | .NET Framework 4.7 |
|`Switch.UseLegacyAccessibilityFeatures`|컨트롤이 내게 필요한 옵션 기능을 사용할 수 있는.NET Framework 4.7.1부터 여부를 설정 또는 해제 합니다. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|내게 필요한 옵션 기능은.NET Framework 4.7.2에서에서 사용할 수 있는지 여부는 사용 하도록 설정 하는 컨트롤 (`false`) 또는 사용 안 함 (`true`). 하는 경우 `true`, `Switch.UseLegacyAccessibilityFeatures` 수도 있어야 `true` .NET Framework 4.7.1 내게 필요한 옵션 기능을 사용 하도록 설정 합니다.|.NET Framework 4.7.2|
|`System.Xml.`<br /><br /> `IgnoreEmptyKeySequences`|XSD 스키마 유효성 검사 하 여 복합 키에 빈 키 시퀀스가 무시할지 여부를 제어 합니다. 자세한 내용은 [완화: XML 스키마 유효성 검사](~/docs/framework/migration-guide/mitigation-xml-schema-validation.md)합니다.|.NET Framework 4.6|  
  
> [!NOTE]
>  추가 하는 대신는 `AppContextSwitchOverrides` 응용 프로그램 구성 파일에 요소를 설정할 수도 있습니다 스위치를 프로그래밍 방식으로 호출 하 여 합니다 `static` (in C#) 또는 `Shared` (Visual Basic)에서는 <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> 메서드.  
  
 라이브러리 개발자는 해당 라이브러리의 이후 버전에서 도입 되거나 변경 된 기능을 옵트아웃 하려면 호출자를 허용 하는 사용자 지정 스위치를 정의할 수도 있습니다. 자세한 내용은 <xref:System.AppContext> 클래스를 참조하세요.  
  
## <a name="example"></a>예  
 다음 예제에서는 합니다 `AppContextSwitchOverrides` 단일 응용 프로그램 호환성 스위치를 정의 하는 요소 `Switch.System.Globalization.NoAsyncCurrentCulture`, 비동기 메서드 호출에서 스레드 간에 흐르지 문화권에 맞지 않는 합니다.  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
   </runtime>  
</configuration>  
```  
  
 다음 예제에서는 합니다 `AppContextSwitchOverrides` 두 개의 응용 프로그램 호환성 스위치를 정의 하는 요소 `Switch.System.Globalization.NoAsyncCurrentCulture` 및 `Switch.System.IO.BlockLongPaths`합니다. 세미콜론으로 구분 된 두 개의 이름/값 쌍을 note 합니다.  
  
```xml  
<configuration>  
    <runtime>  
       <AppContextSwitchOverrides   
          value="Switch.System.Globalization.NoAsyncCurrentCulture=true;Switch.System.IO.BlockLongPaths=true" />  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.AppContext?displayProperty=nameWithType>  
 [\<런타임 > 요소](runtime-element.md)  
 [\<configuration> 요소](../configuration-element.md)
