---
title: "-langversion(C# 컴파일러 옵션)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
caps.latest.revision: "33"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7d3d59f63102ccf3c1d54e4028635c8daad56164
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/06/2017
---
# <a name="langversion-c-compiler-options"></a>/langversion (C# 컴파일러 옵션)
컴파일러가 선택한 C# 언어 사양에 포함된 구문만 허용하도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
/langversion:option  
```  
  
## <a name="arguments"></a>인수  
 `option`  
 유효한 값은 다음과 같습니다.  
  
|옵션|의미|  
|------------|-------------|  
|default|컴파일러가 지원할 수 있는 유효한 언어 구문을 모두 허용합니다. <sup id="TDefault">[Default](#FDefault)</sup>| 
|ISO-1|컴파일러가 ISO/IEC 23270:2003 C#(1.0/1.1)에 포함된 구문만 허용합니다. <sup id="TISO1">[ISO1](#FISO1)</sup>|  
|ISO-2|컴파일러가 ISO/IEC 23270:2006 C#(2.0)에 포함된 구문만 허용합니다. <sup id="TISO2">[ISO2](#FISO2)</sup>|
|3|컴파일러가 C# 3.0 또는 이전 버전에 포함된 구문만 허용합니다. <sup id="TCS3">[CS3](#FCS3)</sup>|
|4|컴파일러가 C# 4.0 또는 이전 버전에 포함된 구문만 허용합니다. <sup id="TCS4">[CS4](#FCS4)</sup>|
|5|컴파일러가 C# 5.0 또는 이전 버전에 포함된 구문만 허용합니다. <sup id="TCS5">[CS5](#FCS5)</sup>|
|6|컴파일러가 C# 6.0 또는 이전 버전에 포함된 구문만 허용합니다. <sup id="TCS6">[CS6](#FCS6)</sup>|
|7|컴파일러가 C# 7.0 또는 이전 버전에 포함된 구문만 허용합니다. <sup id="TCS7">[CS7](#FCS7)</sup>|
|latest|컴파일러가 지원할 수 있는 유효한 언어 구문을 모두 허용합니다. <sup id="TLatest">[Latest](#FLatest)</sup>|
<!--- Uncomment and move these above
|latest| once they're officially released
|7.1|The compiler accepts only syntax that is included in C# 7.1 or lower <sup id="TCS71">[CS71](#FCS71)</sup>|
|7.2|The compiler accepts only syntax that is included in C# 7.2 or lower <sup id="TCS71">[CS72](#FCS72)</sup>|
|8|The compiler accepts only syntax that is included in C# 8 or lower <sup id="TCS71">[CS8](#FCS8)</sup>|
-->

  
## <a name="remarks"></a>설명  
 C# 응용 프로그램에서 참조된 메타데이터에는 **/langversion** 컴파일러 옵션이 적용되지 않습니다.  
  
 각 C# 컴파일러 버전에 언어 사양의 확장이 포함되어 있으므로 **/langversion**은 이전 컴파일러 버전의 동등한 기능을 제공하지 않습니다.  
 
 또한 C# 버전 업데이트는 일반적으로 주 .NET Framework 릴리스와 일치하는 반면, 새 구문과 기능이 반드시 특정 프레임워크 버전에 연결되지는 않습니다. 새로운 기능에는 C# 버전과 함께 릴리스된 새 컴파일러 업데이트가 분명히 필요하지만, 각 특정 기능에 고유한 최소 .Net API 또는 공용 언어 런타임 요구 사항이 있으므로 NuGet 패키지 또는 다른 라이브러리를 포함하여 하위 수준 프레임워크에서 실행이 허용될 수도 있습니다.
  
 사용하는 **/langversion** 설정과 관계없이 현재 버전의 공용 언어 런타임을 사용하여 고유한 .exe 또는 .dll을 만듭니다. 한 가지 예외는 friend 어셈블리와 [/moduleassemblyname(C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md)으로, **/langversion:ISO-1**에서 작동합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트 **속성** 페이지를 엽니다.  
  
2.  **빌드** 속성 페이지를 클릭합니다.  
  
3.  **고급** 단추를 클릭합니다.  
  
4.  **언어 버전** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>을 참조하십시오.  
    
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)  
 [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)  
 
### <a name="c-language-specification"></a>C# 언어 사양
 [C# 언어 사양 참조](../../../csharp/language-reference/language-specification/index.md): .NET Foundation  
 C# 1.0/1.1 [ISO/IEC 23270:2003](https://www.iso.org/standard/36768.html) 정보 기술 - C# 언어 사양: ISO 카탈로그  
 C# 2.0 [ISO/IEC 23270:2006](https://www.iso.org/standard/42926.html) 정보 기술 - C# 언어 사양: ISO 카탈로그  
 C# 2.0 [c042926_ISO_IEC_23270_2006 (E).zip](http://standards.iso.org/ittf/PubliclyAvailableStandards/c042926_ISO_IEC_23270_2006(E).zip) ISO/IEC 23270:2006(PDF 형식): ISO 자유롭게 사용할 수 있는 표준  
 C# 3.0 [CSharp Language Specification.doc](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc) C# 언어 사양 버전 3.0: Microsoft Corporation  
 C# 4.0 [Ecma-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf) 표준 ECMA-334 네 번째 버전    
 C# 5.0 [CSharp Language Specification.docx](https://www.microsoft.com/download/details.aspx?id=7029) C# 언어 사양 버전 5.0: Microsoft Corporation  
 C# 6.0 [README.md](https://github.com/dotnet/csharplang/blob/master/spec/README.md) C# 언어 사양 버전 6 - 비공식 초안: .NET Foundation  
 C# 7.0(현재 사용할 수 없음)  

<!--- Uncomment and add to the above when they become officially released
 C# 7.1 (spec is not yet finished)  
 C# 7.2 (spec is not yet finished)  
 C# 8.0 (spec is not yet finished)  
-->

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a>모든 언어 기능을 지원하는 데 필요한 최소 컴파일러 버전   
[↩](#TDefault)<a name="FDefault">Default</a>, <a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .Net 2002 또는 번들된 .Net Framework 1.0 컴파일러     
[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 또는 번들된 .Net Framework 2.0 컴파일러    
[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 또는 번들된 .Net Framework 3.5 컴파일러    
[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 또는 번들된 .Net Framework 4.0 컴파일러    
[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 또는 번들된 .Net Framework 4.5 컴파일러    
[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015    
[↩](#TCS7)<a name="FCS7">CS7</a>, <a name="FLatest">Latest</a>: Microsoft Visual Studio/Build Tools 2017   

<!--- Uncomment and add to the above when they become officially released
[↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS8)<a name="FCS71">CS8</a>: Microsoft Visual Studio/Build Tools 20??    
-->
