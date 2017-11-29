---
title: "사용자 지정 형식의 Switch 활동 사용 방법"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 482a48c4-eb83-40c3-a4e2-2f9a8af88b75
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a8a4418c582d00f1163305ce5d63c63c198dbc30
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="usage-of-the-switch-activity-with-custom-types"></a><span data-ttu-id="bc154-102">사용자 지정 형식의 Switch 활동 사용 방법</span><span class="sxs-lookup"><span data-stu-id="bc154-102">Usage of the Switch Activity with Custom Types</span></span>
<span data-ttu-id="bc154-103">이 샘플을 사용 하도록 설정 하는 방법에 설명 된 <!--zz <xref:System.Activities. Statements.Switch`1>--> `xref:System.Activities` Statements.Switch`1?qualifyHint=False&autoUpgrade=True activity to evaluate a user-defined complex type at runtime. In most traditional procedural programming languages, a [switch](http://go.microsoft.com/fwlink/?LinkId=180521) statement selects an execution logic based on the conditional evaluation of a variable. Traditionally, a \`전환 ' 문은 정적으로 평가 될 식입니다.</span><span class="sxs-lookup"><span data-stu-id="bc154-103">This sample describes how to enable a <!--zz <xref:System.Activities. Statements.Switch`1>--> `xref:System.Activities` Statements.Switch`1?qualifyHint=False&autoUpgrade=True activity to evaluate a user-defined complex type at runtime. In most traditional procedural programming languages, a [switch](http://go.microsoft.com/fwlink/?LinkId=180521) statement selects an execution logic based on the conditional evaluation of a variable. Traditionally, a `switch` statement operates on an expression that can be statically evaluated.</span></span> <span data-ttu-id="bc154-104">예를 들어 C#에서는 <xref:System.Boolean>, <xref:System.Int32>, <xref:System.String> 등의 기본 형식과 열거형 형식만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc154-104">For example, in C# this means that only primitive types, such as <xref:System.Boolean>, <xref:System.Int32>, <xref:System.String>, and enumeration types are supported.</span></span>  
  
 <span data-ttu-id="bc154-105">사용자 지정 클래스에서 전환을 사용하도록 설정하려면 런타임에 사용자 지정 복합 형식 값을 계산하도록 논리를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc154-105">To enable switching on a custom class, logic must be implemented to evaluate values of the custom complex type at runtime.</span></span> <span data-ttu-id="bc154-106">이 샘플에서는 `Person`이라는 사용자 지정 복합 형식에서 전환을 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc154-106">This sample demonstrates how to enable switching on a custom complex type named `Person`.</span></span>  
  
-   <span data-ttu-id="bc154-107">사용자 지정 클래스 `Person`에서 <xref:System.ComponentModel.TypeConverter> 특성은 사용자 지정 <xref:System.ComponentModel.TypeConverter>의 이름으로 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc154-107">In the custom class `Person`, a <xref:System.ComponentModel.TypeConverter> attribute is declared with the name of the custom <xref:System.ComponentModel.TypeConverter>.</span></span>  
  
    ```  
    [TypeConverter(typeof(PersonConverter))]  
    public class Person  
    {  
       public string Name { get; set; }  
       public int Age { get; set; }  
    ...  
    ```  
  
-   <span data-ttu-id="bc154-108">사용자 지정 클래스 `Person`에서 <xref:System.Object.Equals%2A> 및 <xref:System.Object.GetHashCode%2A> 클래스가 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc154-108">In the custom class `Person`, the <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> classes are overridden.</span></span>  
  
    ```  
    public override bool Equals(object obj)  
    {  
        Person person = obj as Person;  
  
        if (person != null)  
        {  
            return string.Equals(this.Name, person.Name);  
        }  
  
        return false;  
    }  
  
    public override int GetHashCode()  
    {  
        if (this.Name != null)  
        {  
            return this.Name.GetHashCode();  
        }  
  
        return 0;  
    }  
    ```  
  
-   <span data-ttu-id="bc154-109">사용자 지정 <xref:System.ComponentModel.TypeConverter> 클래스는 사용자 지정 클래스의 인스턴스에서 문자열로 또는 문자열에서 사용자 지정 클래스의 인스턴스로 변환하도록 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc154-109">A custom <xref:System.ComponentModel.TypeConverter> class is implemented that performs the conversion of an instance of the custom class to a string and a string to an instance of a custom class.</span></span>  
  
    ```  
    public class PersonConverter : TypeConverter  
    {  
        public override bool CanConvertFrom(ITypeDescriptorContext context,  
           Type sourceType)  
        {  
            return (sourceType is string);  
        }  
  
        // Overrides the ConvertFrom method of TypeConverter.  
        public override object ConvertFrom(ITypeDescriptorContext context,  
           CultureInfo culture, object value)  
        {  
            if (value == null)  
            {  
                return null;  
            }  
  
            if (value is string)  
            {  
                return new Person  
                {  
                    Name = (string)value  
                };  
            }  
  
            return base.ConvertFrom(context, culture, value);  
        }  
  
        // Overrides the ConvertTo method of TypeConverter.  
        public override object ConvertTo(ITypeDescriptorContext context,  
           CultureInfo culture, object value, Type destinationType)  
        {  
            if (destinationType == typeof(string))  
            {  
                if (value != null)  
                {  
                    return ((Person) value).Name;  
                }  
                else  
                {  
                    return null;  
                }  
            }  
  
            return base.ConvertTo(context, culture, value, destinationType);  
        }  
    }  
    ```  
  
 <span data-ttu-id="bc154-110">이 샘플에 포함되어 있는 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bc154-110">The following files are included in this sample:</span></span>  
  
-   <span data-ttu-id="bc154-111">**Person.cs**: 정의 `Person` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="bc154-111">**Person.cs**: Defines the `Person` class.</span></span>  
  
-   <span data-ttu-id="bc154-112">**PersonConverter.cs**:에 대 한 형식 변환기는 `Person` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="bc154-112">**PersonConverter.cs**: The type converter for the `Person` class.</span></span>  
  
-   <span data-ttu-id="bc154-113">**Sequence.xaml**: 전환 하는 워크플로 `Person` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="bc154-113">**Sequence.xaml**: a workflow that switches over the `Person` type.</span></span>  
  
-   <span data-ttu-id="bc154-114">**Program.cs**: 워크플로 실행 하는 main 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="bc154-114">**Program.cs**: The main function that runs the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="bc154-115">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="bc154-115">To use this sample</span></span>  
  
1.  <span data-ttu-id="bc154-116">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 Switch.sln을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="bc154-116">Load Switch.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="bc154-117">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="bc154-117">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="bc154-118">Ctrl+F5를 눌러 샘플을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bc154-118">Press CTRL + F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bc154-119">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc154-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bc154-120">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="bc154-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bc154-121">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="bc154-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bc154-122">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc154-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Switch`  
  
## <a name="see-also"></a><span data-ttu-id="bc154-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc154-123">See Also</span></span>  
 [<span data-ttu-id="bc154-124">기본 제공 활동 라이브러리</span><span class="sxs-lookup"><span data-stu-id="bc154-124">Built-In Activity Library</span></span>](../../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md)
