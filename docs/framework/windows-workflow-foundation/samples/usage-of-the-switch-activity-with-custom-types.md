---
title: 사용자 지정 형식의 Switch 활동 사용 방법
ms.date: 03/30/2017
ms.assetid: 482a48c4-eb83-40c3-a4e2-2f9a8af88b75
ms.openlocfilehash: 2b6f3109324064cb5e746de9c61e5a70c4c4d60b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517883"
---
# <a name="usage-of-the-switch-activity-with-custom-types"></a>사용자 지정 형식의 Switch 활동 사용 방법
이 샘플에서는 <xref:System.Activities.Statements.Switch%601> 활동을 사용하도록 설정하여 런타임에 사용자 정의 복합 형식을 계산하는 방법에 대해 설명합니다. 가장 일반적인 절차적 프로그래밍 언어는 [전환](http://go.microsoft.com/fwlink/?LinkId=180521) 문은 변수의 조건부 계산에 따라 실행 논리를 선택 합니다. 일반적으로 `switch` 문은 정적으로 계산할 수 있는 식에 대해 작동합니다. 예를 들어 C#에서는 <xref:System.Boolean>, <xref:System.Int32>, <xref:System.String> 등의 기본 형식과 열거형 형식만 지원됩니다.  
  
 사용자 지정 클래스에서 전환을 사용하도록 설정하려면 런타임에 사용자 지정 복합 형식 값을 계산하도록 논리를 구현해야 합니다. 이 샘플에서는 `Person`이라는 사용자 지정 복합 형식에서 전환을 사용하도록 설정하는 방법을 보여 줍니다.  
  
-   사용자 지정 클래스 `Person`에서 <xref:System.ComponentModel.TypeConverter> 특성은 사용자 지정 <xref:System.ComponentModel.TypeConverter>의 이름으로 선언됩니다.  
  
    ```  
    [TypeConverter(typeof(PersonConverter))]  
    public class Person  
    {  
       public string Name { get; set; }  
       public int Age { get; set; }  
    ...  
    ```  
  
-   사용자 지정 클래스 `Person`에서 <xref:System.Object.Equals%2A> 및 <xref:System.Object.GetHashCode%2A> 클래스가 재정의됩니다.  
  
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
  
-   사용자 지정 <xref:System.ComponentModel.TypeConverter> 클래스는 사용자 지정 클래스의 인스턴스에서 문자열로 또는 문자열에서 사용자 지정 클래스의 인스턴스로 변환하도록 구현됩니다.  
  
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
  
 이 샘플에 포함되어 있는 파일은 다음과 같습니다.  
  
-   **Person.cs**: 정의 `Person` 클래스입니다.  
  
-   **PersonConverter.cs**:에 대 한 형식 변환기는 `Person` 클래스입니다.  
  
-   **Sequence.xaml**: 전환 하는 워크플로 `Person` 유형입니다.  
  
-   **Program.cs**: 워크플로 실행 하는 main 함수입니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 Switch.sln을 로드합니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl+F5를 눌러 샘플을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Switch`  
  
## <a name="see-also"></a>참고 항목  
 [기본 제공 활동 라이브러리](../../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md)
