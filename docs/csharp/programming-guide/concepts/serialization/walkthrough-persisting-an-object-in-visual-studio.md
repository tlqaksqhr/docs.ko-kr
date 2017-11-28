---
title: "연습: Visual Studio에서 개체 유지(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: get-started-article
ms.assetid: a544ce46-ee25-49da-afd4-457a3d59bf63
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: efdf4694c1a1b6df2e9531a2bb4c813b536a330e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-persisting-an-object-in-visual-studio-c"></a>연습: Visual Studio에서 개체 유지(C#)
디자인 타임에 개체의 속성을 기본값으로 설정할 수 있지만, 런타임에 입력한 값은 개체가 소멸될 때 손실됩니다. serialization을 사용하면 인스턴스 간에 개체의 데이터를 유지할 수 있으므로, 다음에 개체를 인스턴스화할 때 값을 저장하고 검색할 수 있습니다.  
  
 이 연습에서는 간단한 `Loan` 개체를 만들고 데이터를 파일에 유지합니다. 그런 다음 개체를 다시 만들 때 파일에서 데이터를 검색합니다.  
  
> [!IMPORTANT]
>  이 예제에서는 파일이 아직 없는 경우 새 파일을 만듭니다. 응용 프로그램에서 파일을 만들어야 하는 경우 해당 응용 프로그램은 폴더에 대한 `Create` 권한이 있어야 합니다. 권한은 액세스 제어 목록을 사용하여 설정됩니다. 파일이 이미 있는 경우, 응용 프로그램에는 더 낮은 권한인 `Write` 권한만 필요합니다. 가능한 경우 배포하는 동안 파일을 만드는 것이 안전하며, 폴더에 대한 Create 권한 대신 단일 파일에 대해 `Read` 권한만 부여하는 것이 더 안전합니다. 또한 루트 폴더나 Program Files 폴더보다 사용자 폴더에 데이터를 쓰는 것이 더 안전합니다.  
  
> [!IMPORTANT]
>  이 예제에서는 이진 형식 파일의 데이터를 저장합니다. 이러한 형식은 암호 또는 신용 카드 정보와 같은 중요한 데이터에 사용하면 안 됩니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 클릭합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="creating-the-loan-object"></a>Loan 개체 만들기  
 첫 번째 단계는 `Loan` 클래스와 이 클래스를 사용하는 테스트 응용 프로그램을 만드는 것입니다.  
  
### <a name="to-create-the-loan-class"></a>Loan 클래스를 만들려면  
  
1.  새 클래스 라이브러리 프로젝트를 만들고 "LoanClass"라는 이름을 지정합니다. 자세한 내용은 [솔루션 및 프로젝트 만들기](/visualstudio/ide/creating-solutions-and-projects)를 참조하세요.  
  
2.  **솔루션 탐색기**에서 Class1 파일에 대한 바로 가기 메뉴를 열고 **이름 바꾸기**를 선택합니다. 파일 이름을 `Loan`으로 바꾸고 ENTER 키를 누릅니다. 파일 이름을 바꾸면 클래스 이름도 `Loan`으로 바뀝니다.  
  
3.  클래스에 다음 공용 멤버를 추가합니다.  
  
    ```csharp  
    public class Loan : System.ComponentModel.INotifyPropertyChanged  
    {  
        public double LoanAmount {get; set;}  
        public double InterestRate {get; set;}  
        public int Term {get; set;}  
  
        private string p_Customer;  
        public string Customer  
        {  
            get { return p_Customer; }  
            set   
            {  
                p_Customer = value;  
                PropertyChanged(this,  
                  new System.ComponentModel.PropertyChangedEventArgs("Customer"));  
            }  
        }  
  
        public event System.ComponentModel.PropertyChangedEventHandler PropertyChanged;  
  
        public Loan(double loanAmount,  
                    double interestRate,  
                    int term,  
                    string customer)  
        {  
            this.LoanAmount = loanAmount;  
            this.InterestRate = interestRate;  
            this.Term = term;  
            p_Customer = customer;  
        }  
    }  
    ```  
  
 `Loan` 클래스를 사용하는 간단한 응용 프로그램도 만들어야 합니다.  
  
### <a name="to-create-a-test-application"></a>테스트 응용 프로그램을 만들려면  
  
1.  Windows Forms 응용 프로그램 프로젝트를 솔루션에 추가하려면 **파일** 메뉴에서 **추가**, **새 프로젝트**를 차례로 선택합니다.  
  
2.  **새 프로젝트 추가** 대화 상자에서 **Windows Forms 응용 프로그램**을 선택하고, 프로젝트 이름으로 `LoanApp`를 입력한 다음, **확인**을 클릭하여 대화 상자를 닫습니다.  
  
3.  **솔루션 탐색기**에서 LoanApp 프로젝트를 선택합니다.  
  
4.  **프로젝트** 메뉴에서 **시작 프로젝트로 설정**을 선택합니다.  
  
5.  **프로젝트** 메뉴에서 **참조 추가**를 선택합니다.  
  
6.  **참조 추가** 대화 상자에서 **프로젝트** 탭을 선택한 다음 LoanClass 프로젝트를 선택합니다.  
  
7.  **확인** 을 클릭하여 대화 상자를 닫습니다.  
  
8.  디자이너에서 <xref:System.Windows.Forms.TextBox> 컨트롤 4개를 폼에 추가합니다.  
  
9. 코드 편집기에서 다음 코드를 추가합니다.  
  
    ```csharp  
    private LoanClass.Loan TestLoan = new LoanClass.Loan(10000.0, 0.075, 36, "Neil Black");  
  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        textBox1.Text = TestLoan.LoanAmount.ToString();  
        textBox2.Text = TestLoan.InterestRate.ToString();  
        textBox3.Text = TestLoan.Term.ToString();  
        textBox4.Text = TestLoan.Customer;  
    }  
    ```  
  
10. 다음 코드를 사용하여 `PropertyChanged` 이벤트에 대한 이벤트 처리기를 양식에 추가합니다.  
  
    ```csharp  
    private void CustomerPropertyChanged(object sender,   
        System.ComponentModel.PropertyChangedEventArgs e)  
    {  
        MessageBox.Show(e.PropertyName + " has been changed.");  
    }  
    ```  
  
 이 시점에서 응용 프로그램을 빌드 및 실행할 수 있습니다. `Loan` 클래스의 기본값이 텍스트 상자에 나타납니다. 금리 값을 7.5에서 7.1로 변경한 다음 응용 프로그램을 닫고 다시 실행합니다. 값이 기본값인 7.5로 돌아갑니다.  
  
 현실 세계에서 금리는 주기적으로 변경되지만, 애플리케이션이 실행될 때마다 변경되는 것은 아닙니다. 응용 프로그램이 실행될 때마다 사용자가 금리를 업데이트하도록 하는 대신 응용 프로그램 인스턴스 간에 가장 최근의 금리를 유지하는 것이 좋습니다. 다음 단계에서는 Loan 클래스에 serialization을 추가하여 이를 수행합니다.  
  
## <a name="using-serialization-to-persist-the-object"></a>Serialization을 사용하여 개체 유지  
 Loan 클래스의 값을 유지하려면 먼저 클래스를 `Serializable` 속성으로 표시해야 합니다.  
  
### <a name="to-mark-a-class-as-serializable"></a>클래스를 serialize로 표시하려면  
  
-   Loan 클래스에 대한 클래스 선언을 다음과 같이 변경합니다.  
  
    ```csharp  
    [Serializable()]  
    public class Loan : System.ComponentModel.INotifyPropertyChanged  
    {  
    ```  
  
 `Serializable` 특성은 클래스의 모든 내용을 파일에 유지할 수 있음을 컴파일러에 알립니다. `PropertyChanged` 이벤트는 Windows Form 개체에 의해 처리되므로 serialize할 수 없습니다. `NonSerialized` 특성은 유지해서는 안 되는 클래스 멤버를 표시하는 데 사용할 수 있습니다.  
  
### <a name="to-prevent-a-member-from-being-serialized"></a>멤버가 serialize되지 않게 하려면  
  
-   `PropertyChanged` 이벤트에 대한 선언을 다음과 같이 변경합니다.  
  
    ```csharp  
    [field: NonSerialized()]  
    public event System.ComponentModel.PropertyChangedEventHandler PropertyChanged;  
    ```  
  
 다음 단계는 LoanApp 응용 프로그램에 serialization 코드를 추가하는 것입니다. 클래스를 serialize하여 파일에 쓰려면 <xref:System.IO> 및 <xref:System.Xml.Serialization> 네임스페이스를 사용합니다. 정규화된 이름을 입력하지 않으려면 필요한 클래스 라이브러리에 대한 참조를 추가할 수 있습니다.  
  
### <a name="to-add-references-to-namespaces"></a>네임스페이스에 대한 참조를 추가하려면  
  
-   `Form1` 클래스 맨 위에 다음 문을 추가합니다.  
  
    ```csharp  
    using System.IO;  
    using System.Runtime.Serialization.Formatters.Binary;  
    ```  
  
     이 경우 이진 포맷터를 사용하여 개체를 이진 형식으로 저장합니다.  
  
 다음 단계는 개체를 만들 때 파일에서 개체를 deserialize할 코드를 추가하는 것입니다.  
  
### <a name="to-deserialize-an-object"></a>개체를 deserialize하려면  
  
1.  Serialize된 데이터의 파일 이름에 대해 클래스에 상수를 추가합니다.  
  
    ```csharp  
    const string FileName = @"..\..\SavedLoan.bin";  
    ```  
  
2.  다음과 같이 `Form1_Load` 이벤트 프로시저에서 코드를 수정합니다.  
  
    ```csharp  
    private LoanClass.Loan TestLoan = new LoanClass.Loan(10000.0, 0.075, 36, "Neil Black");  
  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        if (File.Exists(FileName))  
        {  
            Stream TestFileStream = File.OpenRead(FileName);  
            BinaryFormatter deserializer = new BinaryFormatter();  
            TestLoan = (LoanClass.Loan)deserializer.Deserialize(TestFileStream);  
            TestFileStream.Close();  
        }  
  
        TestLoan.PropertyChanged += this.CustomerPropertyChanged;  
  
        textBox1.Text = TestLoan.LoanAmount.ToString();  
        textBox2.Text = TestLoan.InterestRate.ToString();  
        textBox3.Text = TestLoan.Term.ToString();  
        textBox4.Text = TestLoan.Customer;  
    }  
    ```  
  
     먼저 파일이 있는지를 확인해야 합니다. 파일이 있으면 이진 파일을 읽는 <xref:System.IO.Stream> 클래스와 파일을 변환하는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 클래스를 만듭니다. 또한 스트림 형식에서 Loan 개체 형식으로 변환해야 합니다.  
  
 그런 다음 텍스트 상자에 입력된 데이터를 `Loan` 클래스에 저장하는 코드를 추가하고, 클래스를 파일로 serialize해야 합니다.  
  
### <a name="to-save-the-data-and-serialize-the-class"></a>데이터를 저장하고 클래스를 serialize하려면  
  
-   다음 코드를 `Form1_FormClosing` 이벤트 프로시저에 추가합니다.  
  
    ```csharp  
    private void Form1_FormClosing(object sender, FormClosingEventArgs e)  
    {  
        TestLoan.LoanAmount = Convert.ToDouble(textBox1.Text);  
        TestLoan.InterestRate = Convert.ToDouble(textBox2.Text);  
        TestLoan.Term = Convert.ToInt32(textBox3.Text);  
        TestLoan.Customer = textBox4.Text;  
  
        Stream TestFileStream = File.Create(FileName);  
        BinaryFormatter serializer = new BinaryFormatter();  
        serializer.Serialize(TestFileStream, TestLoan);  
        TestFileStream.Close();  
    }  
    ```  
  
 이 시점에서 다시 응용 프로그램을 빌드 및 실행할 수 있습니다. 처음에는 텍스트 상자에 기본값이 나타납니다. 값을 변경하고 네 번째 텍스트 상자에 이름을 입력합니다. 응용 프로그램을 닫았다가 다시 엽니다. 이제 새 값이 텍스트 상자에 나타납니다.  
  
## <a name="see-also"></a>참고 항목  
 [serialization(C#)](../../../../csharp/programming-guide/concepts/serialization/index.md)  
 [C# 프로그래밍 가이드](../../../../csharp/programming-guide/index.md)
