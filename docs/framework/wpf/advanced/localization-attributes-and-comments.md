---
title: "지역화 특성 및 주석 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "지역화(localization), 특성"
  - "지역화(localization), 주석"
ms.assetid: ead2d9ac-b709-4ec1-a924-39927a29d02f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 지역화 특성 및 주석
[!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 소스 코드 내의 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 지역화 주석과 속성은 지역화에 대한 규칙과 힌트를 제공하기 위해 개발자에 의해 제공됩니다.  [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 지역화 주석에는 두 가지 정보 집합인 지역화 가능성 특성 및 자유 형식 지역화 주석이 포함됩니다.  지역화 가능성 특성은 지역화할 리소스를 나타내기 위해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 지역화 API에 사용됩니다.  자유 형식 주석은 응용 프로그램 작성자가 포함하고 싶어하는 모든 정보입니다.  
  
   
  
<a name="Localizer_Comments_"></a>   
## 지역화 주석  
 태그 응용 프로그램 작성자는 텍스트 길이, 글꼴 패밀리 또는 글꼴 크기에 대한 제약 조건과 같은 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]의 특정 요소에 대한 요구 사항을 가진 경우 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 코드에서 주석을 사용하여 이 정보를 지역화 담당자에게 전달할 수 있습니다.  주석을 소스 코드에 추가하는 프로세스는 다음과 같습니다.  
  
1.  응용 프로그램 개발자는 지역화 주석을 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 소스 코드에 추가합니다.  
  
2.  빌드 프로세스 중에 자유 형식 지역화 주석을 어셈블리에 둘지, 주석의 일부를 제거할지, 아니면 모든 주석을 제거할지 여부를 .proj 파일에서 지정할 수 있습니다.  제거된 주석은 별개의 파일에 놓입니다.  `LocalizationDirectivesToLocFile` 태그를 사용하여 옵션을 지정합니다. 예를 들면 다음과 같습니다.  
  
     `<LocalizationDirectivesToLocFile>` *value* `</LocalizationDirectivesToLocFile>`  
  
3.  할당할 수 있는 값은 다음과 같습니다.  
  
    -   **None** \- 주석과 특성이 모두 어셈블리 안에 유지되고 별개의 파일이 생성되지 않습니다.  
  
    -   **CommentsOnly** \- 어셈블리에서 주석만 제거하고 별개의 LocFile 파일에 둡니다.  
  
    -   **All** \- 주석과 특성을 어셈블리에서 모두 제거하고 둘 다 별개의 LocFile에 둡니다.  
  
4.  지역화 가능한 리소스가 [!INCLUDE[TLA2#tla_baml](../../../../includes/tla2sharptla-baml-md.md)]에서 추출된 경우 지역화 가능성 특성이 [!INCLUDE[TLA2#tla_baml](../../../../includes/tla2sharptla-baml-md.md)] 지역화 API에서 고려됩니다.  
  
5.  자유 형식 주석만 포함하는 지역화 주석 파일은 나중에 지역화 프로세스에 통합됩니다.  
  
 다음 예제에서는 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 파일에 지역화 주석을 추가하는 방법을 보여 줍니다.  
  
 `<TextBlock x:Id = "text01"`  
  
 `FontFamily = "Microsoft Sans Serif"`  
  
 `FontSize = "12"`  
  
 `Localization.Attributes = "$Content (Unmodifiable Readable Text)`  
  
 `FontFamily (Unmodifiable Readable)"`  
  
 `Localization.Comments = "$Content (Trademark)`  
  
 `FontSize (Trademark font size)" >`  
  
 `Microsoft`  
  
 `</TextBlock>`  
  
 위 샘플에서 Localization.Attributes 섹션에는 지역화 특성이 포함되어 있고 Localization.Comments 섹션에는 자유 형식 주석이 포함되어 있습니다.  다음 표에서는 특성 및 주석과 이러한 특성 및 주석이 지역화 담당자에게 어떤 의미가 있는지 보여 줍니다.  
  
|지역화 특성|의미|  
|------------|--------|  
|$Content \(Unmodifiable Readable Text\)|TextBlock 요소의 콘텐츠를 수정할 수 없습니다.  지역화 담당자는 "Microsoft" 단어를 변경할 수 없습니다.  콘텐츠는 지역화 담당자에게 표시됩니다\(Readable\).  콘텐츠의 범주는 텍스트입니다.|  
|FontFamily \(Unmodifiable Readable\)|TextBlock 요소의 글꼴 패밀리 속성을 변경할 수 없지만 지역화 담당자에게 표시됩니다.|  
  
|지역화 자유 형식 주석|의미|  
|------------------|--------|  
|$Content \(Trademark\)|응용 프로그램 작성자는 TextBlock 요소의 콘텐츠가 상표라는 것을 지역화 담당자에게 알립니다.|  
|FontSize \(Trademark font size\)|응용 프로그램 작성자는 글꼴 크기 속성이 표준 상표 크기를 따라야 한다는 것을 나타냅니다.|  
  
### 지역화 가능성 특성  
 Localization.Attributes의 정보에는 대상 값 이름 및 연관된 지역화 가능성 값 쌍의 목록이 포함됩니다.  대상 이름은 속성 이름 또는 특수한 $Content 이름일 수 있습니다.  속성 이름인 경우 대상 값은 속성의 값입니다.  $Content인 경우 대상 값은 요소의 콘텐츠입니다.  
  
 다음 세 가지 형식의 특성이 있습니다.  
  
-   **Category**.  지역화 담당자 도구에서 값을 수정할 수 있어야 하는지 여부를 지정합니다.  <xref:System.Windows.LocalizabilityAttribute.Category%2A>를 참조하십시오.  
  
-   **Readability**.  지역화 담당자 도구에서 값을 읽고 표시해야 하는지 여부를 지정합니다.  <xref:System.Windows.LocalizabilityAttribute.Readability%2A>를 참조하십시오.  
  
-   **Modifiability**.  지역화 담당자 도구에서 값 수정을 허용하는지 여부를 지정합니다.  <xref:System.Windows.LocalizabilityAttribute.Modifiability%2A>를 참조하십시오.  
  
 이러한 특성은 공백으로 구분하여 순서에 관계없이 지정할 수 있습니다.  중복된 특성이 지정된 경우 마지막 특성이 이전 특성을 재정의합니다.  예를 들어 Localization.Attributes \= "Unmodifiable Modifiable"은 Modifiability를 마지막 값인 Modifiable로 설정합니다.  
  
 Modifiability 및 Readability는 이름만으로도 해당 의미를 이해할 수 있습니다.  Category 특성은 지역화 담당자가 텍스트를 번역할 때 도움이 되는 미리 정의된 범주를 제공합니다.  Text, Label 및 Title과 같은 범주는 텍스트를 번역하는 방법에 대한 정보를 지역화 담당자에게 제공합니다.  또한 None, Inherit, Ignore, NeverLocalize 등과 같은 특수한 범주가 있습니다.  
  
 다음 표에는 특수한 범주의 의미를 보여 줍니다.  
  
|범주|의미|  
|--------|--------|  
|없음|대상 값에 정의된 범주가 없습니다.|  
|Inherit|대상 값이 부모로부터 범주를 상속합니다.|  
|Ignore|대상 값이 지역화 프로세스에서 무시됩니다.  Ignore는 현재 값에만 영향을 줍니다.  자식 노드에는 영향을 주지 않습니다.|  
|NeverLocalize|현재 값을 지역화할 수 없습니다.  이 범주는 요소의 자식에 의해 상속됩니다.|  
  
<a name="Localization_Comments"></a>   
## 지역화 주석  
 Localization.Comments에는 대상 값에 대한 자유 형식 문자열이 포함됩니다.  응용 프로그램 개발자는 응용 프로그램 텍스트를 번역하는 방법에 대한 힌트를 지역화 담당자에게 제공하기 위해 정보를 추가할 수 있습니다.  주석 형식은 "\(\)"로 묶인 모든 문자열이 될 수 있습니다.  문자를 이스케이프하려면 '\\'를 사용합니다.  
  
## 참고 항목  
 [WPF의 전역화](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)   
 [자동 레이아웃을 사용하여 단추 만들기](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)   
 [자동 레이아웃에 Grid 사용](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)   
 [응용 프로그램 지역화](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)