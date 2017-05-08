---
title: "데스크톱 응용 프로그램용 리소스 파일 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".resources 파일"
  - "응용 프로그램 리소스, 파일 만들기"
  - "리소스 파일, .resources 파일"
  - "리소스 파일, 만들기"
ms.assetid: 6c5ad891-66a0-4e7a-adcf-f41863ba6d8d
caps.latest.revision: 25
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 25
---
# 데스크톱 응용 프로그램용 리소스 파일 만들기
응용 프로그램에서 쉽게 사용할 수 있도록 문자열, 이미지 또는 개체 데이터와 같은 리소스를 리소스 파일에 포함할 수 있습니다.  .NET Framework에서는 리소스 파일을 만드는 5가지 방법을 제공합니다.  
  
-   문자열 리소스가 포함된 텍스트 파일을 만듭니다.  [리소스 파일 생성기\(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)를 사용하여 텍스트 파일을 이진 리소스 파일\(.resources\)로 변환할 수 있습니다.  그런 다음 이진 리소스 파일을 언어 컴파일러를 사용하여 응용 프로그램 실행 파일이나 응용 프로그램 라이브러리에 포함하거나, [어셈블리 링커\(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md)를 사용하여 위성 어셈블리에 포함할 수 있습니다.  자세한 내용은, [텍스트 파일의 리소스](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#TextFiles) 섹션을 참조하십시오.  
  
-   문자열, 이미지 또는 개체 데이터가 포함된 XML 리소스 파일\(.resx\)을 만듭니다.  [리소스 파일 생성기\(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)를 사용하여 .resx 파일을 이진 리소스 파일\(.resources\)로 변환할 수 있습니다.  그런 다음 이진 리소스 파일을 언어 컴파일러를 사용하여 응용 프로그램 실행 파일이나 응용 프로그램 라이브러리에 포함하거나, [어셈블리 링커\(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md)를 사용하여 위성 어셈블리에 포함할 수 있습니다.  자세한 내용은 [.resx 파일의 리소스](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#ResxFiles) 섹셤을 참조하십시오.  
  
-   <xref:System.Resources> 네임스페이스의 형식을 사용하여 프로그래밍 방식으로 XML 리소스 파일\(.resx\)을 만듭니다.  .resx 파일을 만들고, 해당 리소스를 열거하고, 이름별로 특정 리소스를 검색할 수 있습니다.  자세한 내용은 [프로그래밍 방식으로 .resx 파일 작업](../../../docs/framework/resources/working-with-resx-files-programmatically.md) 항목을 참조하십시오.  
  
-   프로그래밍 방식으로 이진 리소스 파일\(.resources\)을 만듭니다.  그런 다음 이 파일을 언어 컴파일러를 사용하여 응용 프로그램 실행 파일이나 응용 프로그램 라이브러리에 포함하거나, [어셈블리 링커\(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md)를 사용하여 위성 어셈블리에 포함할 수 있습니다.  자세한 내용은 [.resources 파일의 리소스](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#ResourcesFiles) 섹션을 참조하십시오.  
  
-   Visual Studio를 사용하여 리소스 파일을 만들고 프로젝트에 포함합니다.  Visual Studio에서는 리소스를 추가, 삭제 및 수정하는 데 사용할 수 있는 리소스 편집기를 제공합니다.  컴파일 타임에 리소스 파일은 자동으로 이진 .resources 파일로 변환되고 응용 프로그램 어셈블리나 위성 어셈블리에 포함됩니다.  자세한 내용은 [Visual Studio의 리소스 파일](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#VSResFiles) 섹션을 참조하십시오.  
  
<a name="TextFiles"></a>   
## 텍스트 파일의 리소스  
 텍스트 파일\(.txt 혹은 .restext\)을 사용하면 문자열 리소스만 저장할 수 있습니다. 문자열이 아닌 리소스의 경우, .resx 파일을 사용하거나 프로그래밍 방식으로 .resx 파일을 만듭니다.  문자열 리소스가 포함된 텍스트 파일의 형식은 다음과 같습니다.  
  
```  
# This is an optional comment.  
name = value  
  
; This is another optional comment.  
name = value  
  
; The following supports conditional compilation if X is defined.  
#ifdef X  
name1=value1  
name2=value2  
#endif  
  
# The following supports conditional compilation if Y is undefined.  
#if !Y  
name1=value1  
name2=value2  
#endif  
  
```  
  
 .Restext 및 .txt 파일의 리소스 파일 형식은 같습니다.  .Restext 파일 확장명은 단순히 텍스트 기반 리소스 파일로 텍스트 파일을 즉시 식별할 수 있도록 사용 됩니다.  
  
 스트링 리소스는 *name\/value* 쌍으로 나타나는데, 이것은 *name* 이 리소스를 식별하는 스트링이고, 그리고 *value* 는 당신이 *name* 를 <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=fullName> 와 같은 리소스를 검색하는 메서드를 통과시킬 때 반환되는 리소스 스트링입니다.  *name* 와 *value* 는 등호\(\=\)를 사용하여 구분해야 합니다.  예를 들면 다음과 같습니다.  
  
```  
  
FileMenuName=File  
EditMenuName=Edit  
ViewMenuName=View  
HelpMenuName=Help  
  
```  
  
> [!CAUTION]
>  암호, 보안이 중요한 정보 또는 개인 데이터를 저장할 때는 리소스 파일을 사용하지 마십시오.  
  
 빈 문자열 \(즉, <xref:System.String.Empty?displayProperty=fullName>을 가진 리소스\) 텍스트 파일에는 사용할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
EmptyString=  
```  
  
 다음을 이용하여 시작하고 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], 텍스트 파일은 다음을 이용해서 조건부 컴파일을 지원합니다 `#ifdef` *symbol*...  `#endif` 및 `#if !`*symbol*...  `#endif` 생성자.  그리고 `/define` 스위치와 [리소스 파일 생성기 \(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) 을 기호를 정의하기 위해 사용할 수 있습니다.  각 리소스는 고유한 `#ifdef` *symbol* 을 필요로 합니다...  `#endif` 또는 `#if !`*symbol*...  `#endif` 생성자.  다음 `#ifdef` 명세서를 사용하고 *symbol* 가 정의되면, 연결 된 리소스는 .resources 파일에 포함됩니다; 그렇지 않으면, 포함 되지 않습니다.  다음 `#if !` 명세서를 사용하고 *symbol* 가 정의 되지 않으면, 연결 된 리소스는 .resources 파일에 포함됩니다; 그렇지 않으면, 포함 되지 않습니다.  
  
 주석은 텍스트 파일에서 선택 사항이며 줄 맨 앞에 세미콜론\(;\)이나 파운드 기호\(\#\)가 표시되고 주석이 표시됩니다.  주석이 포함된 줄은 파일의 어느 곳에나 배치할 수 있습니다.  주석은 [리소스 파일 생성기\(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)를 사용하여 만든 컴파일된 .resources 파일에 포함되지 않습니다.  
  
 텍스트 파일의 빈 줄은 공백으로 간주되며 무시됩니다.  
  
 다음 예제에서는 `OKButton`과 `CancelButton`이라는 두 가지 문자열 리소스를 정의합니다.  
  
```  
#Define resources for buttons in the user interface.  
OKButton=OK  
CancelButton=Cancel  
```  
  
 만약 *name*의 출현이 중복 된 텍스트 파일의 경우, [리소스 파일 생성기\(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) 는 경고를 표시하고 두 번째 이름을 무시합니다.  
  
 *value* 는 새 선 문자를 포함할 수 없습니다, 그러나 당신은 `\n` 같은 C 언어 스타일 이스케이프 문자를 새 선을 표현하기 위해 사용할 수 있고 `\t` 를 탭을 표현하기 위해 사용할 수 있습니다.  \(예: "\\\\"\) 이스케이프 된 백슬래시 문자를 포함할 수도 있습니다.  또한 빈 문자열이 허용됩니다.  
  
 little\-endian 또는 big\-endian 바이트 순서의 UTF\-8 인코딩이나 UTF\-16 인코딩을 사용하여 텍스트 파일 형식으로 리소스를 저장해야 합니다.  그러나 .txt 파일을 .resources 파일로 변환하는 [리소스 파일 생성기\(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)에서는 기본적으로 파일을 UTF\-8로 처리합니다.  UTF\-16을 사용하여 인코딩된 파일을 Resgen.exe에서 인식하게 하려면 파일의 처음 부분에 유니코드 바이트 순서 표시\(U\+FEFF\)를 포함해야 합니다.  
  
 텍스트 형식의 리소스 파일을 .NET Framework 어셈블리에 포함하려면 [리소스 파일 생성기\(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)를 사용하여 파일을 이진 리소스 파일\(.resources\)로 변환해야 합니다.  그런 다음 .resources 파일을 언어 컴파일러를 사용하여 .NET Framework 어셈블리에 포함하거나, [어셈블리 링커\(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md)를 사용하여 위성 어셈블리에 포함할 수 있습니다.  
  
 다음 예제에서는 GreetingResources.txt라는 텍스트 형식의 리소스 파일을 간단한 "Hello World" 콘솔 응용 프로그램에 사용합니다.  이 텍스트 파일에서는 사용자에게 이름을 입력하도록 요청하고 인사말을 표시하는 `prompt`와 `greeting`이라는 두 문자열을 정의합니다.  
  
```  
# GreetingResources.txt   
# A resource file in text format for a "Hello World" application.  
#  
# Initial prompt to the user.  
prompt=Enter your name:   
# Format string to display the result.  
greeting=Hello, {0}!  
```  
  
 다음 명령을 사용하여 텍스트 파일이 .resources 파일로 변환됩니다.  
  
 **resgen GreetingResources.txt**  
  
 다음 예제에서는 .resources 파일을 사용하여 사용자에게 메시지를 표시하는 콘솔 응용 프로그램의 소스 코드를 보여 줍니다.  
  
 [!code-csharp[Conceptual.Resources.TextFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.textfiles/cs/greeting.cs#1)]
 [!code-vb[Conceptual.Resources.TextFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.textfiles/vb/greeting.vb#1)]  
  
 Visual Basic을 사용하고 소스 코드 파일의 이름이 Greeting.vb인 경우 다음 명령은 포함된 .resources 파일을 포함하는 실행 파일을 만듭니다.  
  
 **vbc greeting.vb \/resource:GreetingResources.resources**  
  
 C\#을 사용하고 소스 코드 파일의 이름이 Greeting.cs인 경우 다음 명령은 포함된 .resources 파일을 포함하는 실행 파일을 만듭니다.  
  
 **csc greeting.cs \/resource:GreetingResources.resources**  
  
<a name="ResxFiles"></a>   
## .resx 파일의 리소스  
 문자열 리소스만 저장할 수 있는 텍스트 파일과 달리 XML 리소스 파일\(.resx\)은 문자열뿐만 아니라 이미지, 아이콘, 오디오 클립 등의 이진 데이터와 프로그래밍 개체를 저장할 수 있습니다.  .resx 파일은 리소스 엔트리의 형식을 기술하고 데이터를 구문 분석하는 데 사용되는 XML의 버전 관리 정보를 지정하는 표준 헤더를 포함합니다.  XML 헤더 뒤에 리소스 파일 데이터가 표시됩니다.  각 데이터 항목은 `data` 태그에 포함된 이름\/값 쌍으로 구성됩니다.  `name` 특성은 리소스 이름을 정의하고 중첩된 `value` 태그에 리소스 값이 포함됩니다.  문자열 데이터의 경우 `value` 태그에 문자열이 포함됩니다.  
  
 예를 들어 다음 `data` 태그는 값이 "Enter your name:"인 `prompt`라는 문자열 리소스를 정의합니다.  
  
```  
<data name="prompt" xml:space="preserve">  
  <value>Enter your name:</value>  
</data>  
```  
  
> [!WARNING]
>  암호, 보안이 중요한 정보 또는 개인 데이터를 저장할 때는 리소스 파일을 사용하지 마십시오.  
  
 리소스 개체의 경우 **data** 태그에 리소스의 데이터 형식을 나타내는 `type` 특성이 포함됩니다.  이진 데이터로 구성된 개체의 경우 `data` 태그에 이진 데이터의 `base64` 형식을 나타내는 `mimetype` 특성도 포함됩니다.  
  
> [!NOTE]
>  모든 .resx 파일에서는 이진 serialization 포맷터를 사용하여 지정된 형식에 대한 이진 데이터를 생성하고 구문을 분석합니다.  따라서 개체에 대한 이진 serialization 형식이 호환되지 않는 방식으로 변경되면 .resx 파일이 올바르지 않게 될 수 있습니다.  
  
 다음 예제에서는 <xref:System.Int32> 리소스와 비트맵 이미지를 포함하는 .resx 파일의 부분을 보여 줍니다.  
  
```  
  
<data name="i1" type="System.Int32, mscorlib">  
  <value>20</value>  
</data>  
  
<data name="flag" type="System.Drawing.Bitmap, System.Drawing,     
    Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"   
    mimetype="application/x-microsoft.net.object.bytearray.base64">  
  <value>  
    AAEAAAD/////AQAAAAAAAAAMAgAAADtTeX…  
  </value>  
</data>  
```  
  
> [!IMPORTANT]
>  .resx 파일이 미리 정의된 형식의 제대로 구성된 XML로 구성되어야 하기 때문에 특히 .resx 파일에 문자열이 아닌 리소스가 포함된 경우 .resx 파일을 수동으로 사용하지 않는 것이 좋습니다.  대신, Visual Studio에서는 .resx 파일을 만들고 조작하기 위한 투명한 인터페이스를 제공합니다. 자세한 내용은 [Visual Studio의 리소스 파일](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#VSResFiles) 단원을 참조하십시오.  프로그래밍 방식으로 .resx 파일을 만들고 조작할 수도 있습니다.  자세한 내용은 [프로그래밍 방식으로 .resx 파일 작업](../../../docs/framework/resources/working-with-resx-files-programmatically.md)을 참조하십시오.  
  
<a name="ResourcesFiles"></a>   
## .resources 파일의 리소스  
 <xref:System.Resources.ResourceWriter?displayProperty=fullName> 클래스를 사용하여 코드에서 직접 이진 리소스 파일\(.resources\)을 프로그래밍 방식으로 만들 수 있습니다.  [리소스 파일 생성기\(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)를 사용하여 텍스트 파일 또는 .resx 파일에서 .resources 파일을 만들 수도 있습니다.  .resources 파일에는 문자열 데이터뿐만 아니라 이진 데이터\(바이트 배열\)와 개체 데이터가 포함될 수 있습니다.  .resources 파일을 프로그래밍 방식으로 만들려면 다음 단계를 수행해야 합니다.  
  
1.  고유한 파일 이름을 사용하여 <xref:System.Resources.ResourceWriter> 개체를 만듭니다.  파일 이름 또는 파일 스트림을 <xref:System.Resources.ResourceWriter> 클래스 생성자에 지정하여 이 작업을 수행할 수 있습니다.  
  
2.  파일에 추가할 각 명명된 리소스에 대해 <xref:System.Resources.ResourceWriter.AddResource%2A?displayProperty=fullName> 메서드의 오버로드 중 하나를 호출합니다.  리소스는 문자열, 개체 또는 이진 데이터의 컬렉션\(바이트 배열\)일 수 있습니다.  
  
3.  <xref:System.Resources.ResourceWriter.Close%2A?displayProperty=fullName> 메서드를 호출하여 리소스를 파일에 기록하고 <xref:System.Resources.ResourceWriter> 개체를 닫습니다.  
  
> [!NOTE]
>  암호, 보안이 중요한 정보 또는 개인 데이터를 저장할 때는 리소스 파일을 사용하지 마십시오.  
  
 다음 예제에서는 문자열 6개, 아이콘 한 개, 응용 프로그램 정의 개체 2개\(`Automobile` 개체 2개\)를 저장하는 CarResources.resources라는 .resources 파일을 프로그래밍 방식으로 만듭니다.  이 예제에서 정의되고 인스턴스화된 `Automobile` 클래스는 이진 serialization 포맷터에 의해 유지될 수 있도록 하는 <xref:System.SerializableAttribute> 특성으로 태그가 지정됩니다.  
  
 [!code-csharp[Conceptual.Resources.Resources#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resources/cs/resources1.cs#1)]
 [!code-vb[Conceptual.Resources.Resources#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resources/vb/resources1.vb#1)]  
  
 .resources 파일을 만든 후 언어 컴파일러의 `/resource` 스위치를 포함하여 런타임 실행 파일이나 라이브러리에 포함하거나, [어셈블리 링커\(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md)를 사용하여 위성 어셈블리에 포함할 수 있습니다.  
  
<a name="VSResFiles"></a>   
## Visual Studio의 리소스 파일  
 리소스 파일을 Visual Studio 프로젝트에 추가하면 Visual Studio에서는 .resx 파일을 프로젝트 디렉터리에 만듭니다.  Visual Studio에서는 문자열, 이미지 및 이진 개체를 추가하는 데 사용할 수 있는 리소스 편집기를 제공합니다.  편집기가 정적 데이터만 처리하도록 설계되었기 때문에 프로그래밍 개체를 저장하는 데 사용할 수 없습니다. 프로그래밍 방식으로 .resx 파일이나 .resources 파일에 개체 데이터를 기록해야 합니다.  참조는 [프로그래밍 방식으로 .resx 파일 작업](../../../docs/framework/resources/working-with-resx-files-programmatically.md) 항목 및 [.resources 파일의 리소스](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#ResourcesFiles) 단원을 참조하십시오.  
  
 지역화된 리소스를 추가하는 경우 주 리소스 파일과 동일한 루트 파일 이름을 제공해야 하며 파일 이름에 문화권도 지정해야 합니다.  예를 들어 Resources.resx라는 리소스 파일을 추가하는 경우 영어\(미국\) 및 프랑스어\(프랑스\) 문화권의 지역화된 리소스를 저장하기 위해 각각 Resources.en\-US.resx 및 Resources.fr\-FR.resx라는 리소스 파일도 만들 수 있습니다.  응용 프로그램의 기본 문화권도 지정해야 합니다.  기본 문화권은 특정 문화권의 지역화된 리소스를 찾을 수 없는 경우 사용되는 리소스의 문화권입니다.  기본 문화권을 지정하려면 Visual Studio의 솔루션 탐색기에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 응용 프로그램을 가리킨 다음 **어셈블리 정보**를 클릭하고 **중립 언어** 목록에서 적절한 언어\/문화권을 선택합니다.  
  
 컴파일 타임에 Visual Studio에서는 먼저 프로젝트의 .resx 파일을 이진 리소스 파일\(.resources\)로 변환한 다음 프로젝트에 대한 obj 디렉터리의 하위 디렉터리에 저장합니다.  Visual Studio에서는 지역화된 리소스가 포함되지 않은 모든 리소스 파일을 프로젝트에서 생성된 주 어셈블리에 포함합니다.  지역화된 리소스가 포함된 리소스 파일이 있으면 Visual Studio에서는 각 지역화된 문화권에 대한 별도의 위성 어셈블리에 해당 파일을 포함합니다.  그런 다음 각 위성 어셈블리를 지역화된 문화권에 해당하는 이름의 디렉터리에 저장합니다.  예를 들어 지역화된 영어\(미국\) 리소스는 en\-US 하위 디렉터리의 위성 어셈블리에 저장됩니다.  
  
## 참고 항목  
 <xref:System.Resources>   
 [데스크톱 응용 프로그램의 리소스](../../../docs/framework/resources/index.md)   
 [리소스 패키징 및 배포](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)