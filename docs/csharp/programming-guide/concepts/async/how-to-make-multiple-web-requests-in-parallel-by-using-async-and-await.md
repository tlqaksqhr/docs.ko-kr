---
title: '방법: async 및 await를 사용하여 병렬로 여러 웹 요청 만들기(C#)'
ms.date: 07/20/2015
ms.assetid: 19745899-f97a-4499-a7c7-e813d1447580
ms.openlocfilehash: e3e94c6ba475a56b5a2b7069eac1f1bbe45498c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337758"
---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-c"></a><span data-ttu-id="4ab24-102">방법: async 및 await를 사용하여 병렬로 여러 웹 요청 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="4ab24-102">How to: Make Multiple Web Requests in Parallel by Using async and await (C#)</span></span>
<span data-ttu-id="4ab24-103">비동기 메서드에서 작업은 만들어질 때 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-103">In an async method, tasks are started when they’re created.</span></span> <span data-ttu-id="4ab24-104">작업이 완료될 때까지 처리를 계속할 수 없는 메서드 지점의 작업에 [await](../../../../csharp/language-reference/keywords/await.md) 연산자가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-104">The [await](../../../../csharp/language-reference/keywords/await.md) operator is applied to the task at the point in the method where processing can’t continue until the task finishes.</span></span> <span data-ttu-id="4ab24-105">다음 예제와 같이 작업이 생성되는 즉시 대기되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-105">Often a task is awaited as soon as it’s created, as the following example shows.</span></span>  
  
```csharp  
var result = await someWebAccessMethodAsync(url);  
```  
  
 <span data-ttu-id="4ab24-106">그러나 프로그램에서 작업 완료에 의존하지 않는 다른 작업을 수행해야 하는 경우 작업 생성과 작업 대기를 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-106">However, you can separate creating the task from awaiting the task if your program has other work to accomplish that doesn’t depend on the completion of the task.</span></span>  
  
```csharp  
// The following line creates and starts the task.  
var myTask = someWebAccessMethodAsync(url);  
  
// While the task is running, you can do other work that doesn't depend  
// on the results of the task.  
// . . . . .  
  
// The application of await suspends the rest of this method until the task is complete.  
var result = await myTask;  
```  
  
 <span data-ttu-id="4ab24-107">작업 시작과 작업 대기 사이에 다른 작업을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-107">Between starting a task and awaiting it, you can start other tasks.</span></span> <span data-ttu-id="4ab24-108">추가 작업은 암시적으로 병렬로 실행되지만 추가 스레드는 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-108">The additional tasks implicitly run in parallel, but no additional threads are created.</span></span>  
  
 <span data-ttu-id="4ab24-109">다음 프로그램은 세 개의 비동기 웹 다운로드를 시작한 다음 호출된 순서대로 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-109">The following program starts three asynchronous web downloads and then awaits them in the order in which they’re called.</span></span> <span data-ttu-id="4ab24-110">프로그램을 실행할 때 작업이 항상 생성 및 대기된 순서로 완료되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-110">Notice, when you run the program, that the tasks don’t always finish in the order in which they’re created and awaited.</span></span> <span data-ttu-id="4ab24-111">작업은 생성 시 실행을 시작하고, 메서드가 await 식에 도달하기 전에 작업 중 하나 이상이 완료될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-111">They start to run when they’re created, and one or more of the tasks might finish before the method reaches the await expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ab24-112">이 프로젝트를 완료하려면 Visual Studio 2012 이상 및 .NET Framework 4.5 이상이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-112">To complete this project, you must have Visual Studio 2012 or higher and the .NET Framework 4.5 or higher installed on your computer.</span></span>  
  
 <span data-ttu-id="4ab24-113">동시에 여러 작업을 시작하는 다른 예제는 [방법: Task.WhenAll을 사용하여 비동기 연습 확장(C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ab24-113">For another example that starts multiple tasks at the same time, see [How to: Extend the async Walkthrough by Using Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="4ab24-114">이 예제의 코드는 [개발자 코드 샘플](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-114">You can download the code for this example from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e).</span></span>  
  
### <a name="to-set-up-the-project"></a><span data-ttu-id="4ab24-115">프로젝트를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="4ab24-115">To set up the project</span></span>  
  
1.  <span data-ttu-id="4ab24-116">WPF 응용 프로그램을 설정하려면 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-116">To set up a WPF application, complete the following steps.</span></span> <span data-ttu-id="4ab24-117">이러한 단계에 대한 자세한 지침은 [연습: async 및 await를 사용하여 웹에 액세스(C#)](../../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-117">You can find detailed instructions for these steps in [Walkthrough: Accessing the Web by Using async and await (C#)](../../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
    -   <span data-ttu-id="4ab24-118">텍스트 상자와 단추가 포함된 WPF 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-118">Create a WPF application that contains a text box and a button.</span></span> <span data-ttu-id="4ab24-119">단추의 이름을 `startButton`, 텍스트 상자의 이름을 `resultsTextBox`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-119">Name the button `startButton`, and name the text box `resultsTextBox`.</span></span>  
  
    -   <span data-ttu-id="4ab24-120"><xref:System.Net.Http>에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-120">Add a reference for <xref:System.Net.Http>.</span></span>  
  
    -   <span data-ttu-id="4ab24-121">MainWindow.xaml.cs 파일에서 `System.Net.Http`에 대한 `using` 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-121">In the MainWindow.xaml.cs file, add a `using` directive for `System.Net.Http`.</span></span>  
  
### <a name="to-add-the-code"></a><span data-ttu-id="4ab24-122">코드를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="4ab24-122">To add the code</span></span>  
  
1.  <span data-ttu-id="4ab24-123">디자인 창 MainWindow.xaml에서 단추를 두 번 클릭하여 MainWindow.xaml.cs에서 `startButton_Click` 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-123">In the design window, MainWindow.xaml, double-click the button to create the `startButton_Click` event handler in MainWindow.xaml.cs.</span></span>  
  
2.  <span data-ttu-id="4ab24-124">다음 코드를 복사하고 MainWindow.xaml.cs의 `startButton_Click` 본문에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-124">Copy the following code, and paste it into the body of `startButton_Click` in MainWindow.xaml.cs.</span></span>  
  
    ```csharp  
    resultsTextBox.Clear();  
    await CreateMultipleTasksAsync();  
    resultsTextBox.Text += "\r\n\r\nControl returned to startButton_Click.\r\n";  
    ```  
  
     <span data-ttu-id="4ab24-125">코드는 응용 프로그램을 구동하는 비동기 메서드 `CreateMultipleTasksAsync`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-125">The code calls an asynchronous method, `CreateMultipleTasksAsync`, which drives the application.</span></span>  
  
3.  <span data-ttu-id="4ab24-126">프로젝트에 다음과 같은 지원 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-126">Add the following support methods to the project:</span></span>  
  
    -   <span data-ttu-id="4ab24-127">`ProcessURLAsync`는 <xref:System.Net.Http.HttpClient> 메서드를 사용하여 웹 사이트 내용을 바이트 배열로 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-127">`ProcessURLAsync` uses an <xref:System.Net.Http.HttpClient> method to download the contents of a website as a byte array.</span></span> <span data-ttu-id="4ab24-128">그런 다음 지원 메서드 `ProcessURLAsync`는 배열의 길이를 표시하고 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-128">The support method, `ProcessURLAsync` then displays and returns the length of the array.</span></span>  
  
    -   <span data-ttu-id="4ab24-129">`DisplayResults`에 각 URL에 대한 바이트 배열의 바이트 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-129">`DisplayResults` displays the number of bytes in the byte array for each URL.</span></span> <span data-ttu-id="4ab24-130">이 표시는 각 작업의 다운로드가 완료된 시간을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-130">This display shows when each task has finished downloading.</span></span>  
  
     <span data-ttu-id="4ab24-131">다음 메서드를 복사한 다음 MainWindow.xaml.cs의 `startButton_Click` 이벤트 처리기 뒤에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-131">Copy the following methods, and paste them after the `startButton_Click` event handler in MainWindow.xaml.cs.</span></span>  
  
    ```csharp  
    async Task<int> ProcessURLAsync(string url, HttpClient client)  
    {  
        var byteArray = await client.GetByteArrayAsync(url);  
        DisplayResults(url, byteArray);  
        return byteArray.Length;  
    }  
  
    private void DisplayResults(string url, byte[] content)  
    {  
        // Display the length of each website. The string format   
        // is designed to be used with a monospaced font, such as  
        // Lucida Console or Global Monospace.  
        var bytes = content.Length;  
        // Strip off the "http://".  
        var displayURL = url.Replace("http://", "");  
        resultsTextBox.Text += string.Format("\n{0,-58} {1,8}", displayURL, bytes);  
    }  
    ```  
  
4.  <span data-ttu-id="4ab24-132">마지막으로, 다음 단계를 수행하는 `CreateMultipleTasksAsync` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-132">Finally, define method `CreateMultipleTasksAsync`, which performs the following steps.</span></span>  
  
    -   <span data-ttu-id="4ab24-133">이 메서드는 `ProcessURLAsync`의 <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> 메서드에 액세스하는 데 필요한 `HttpClient` 개체를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-133">The method declares an `HttpClient` object,which you need  to access method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> in `ProcessURLAsync`.</span></span>  
  
    -   <span data-ttu-id="4ab24-134">메서드는 `TResult`가 정수인 <xref:System.Threading.Tasks.Task%601> 형식의 세 가지 작업을 만들고 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-134">The method creates and starts three tasks of type <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer.</span></span> <span data-ttu-id="4ab24-135">각 작업이 완료되면 `DisplayResults`에 작업의 URL 및 다운로드한 콘텐츠의 길이가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-135">As each task finishes, `DisplayResults` displays the task's URL and the length of the downloaded contents.</span></span> <span data-ttu-id="4ab24-136">작업이 비동기적으로 실행되므로 결과가 표시되는 순서는 선언된 순서와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-136">Because the tasks are running asynchronously, the order in which the results appear might differ from the order in which they were declared.</span></span>  
  
    -   <span data-ttu-id="4ab24-137">메서드는 각 작업이 완료될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-137">The method awaits the completion of each task.</span></span> <span data-ttu-id="4ab24-138">각 `await` 연산자는 대기된 작업이 완료될 때까지 `CreateMultipleTasksAsync`의 실행을 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-138">Each `await` operator suspends execution of `CreateMultipleTasksAsync` until the awaited task is finished.</span></span> <span data-ttu-id="4ab24-139">또한 연산자는 완료된 각 작업에서 `ProcessURLAsync` 호출의 반환 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-139">The operator also retrieves the return value from the call to `ProcessURLAsync` from each completed task.</span></span>  
  
    -   <span data-ttu-id="4ab24-140">작업이 완료되고 정수 값이 검색된 경우 메서드는 웹 사이트의 길이를 합산하고 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-140">When the tasks have been completed and the integer values have been retrieved, the method sums the lengths of the websites and displays the result.</span></span>  
  
     <span data-ttu-id="4ab24-141">다음 메서드를 복사하고 솔루션에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-141">Copy the following method, and paste it into your solution.</span></span>  
  
    ```csharp  
    private async Task CreateMultipleTasksAsync()  
    {  
        // Declare an HttpClient object, and increase the buffer size. The  
        // default buffer size is 65,536.  
        HttpClient client =  
            new HttpClient() { MaxResponseContentBufferSize = 1000000 };  
  
        // Create and start the tasks. As each task finishes, DisplayResults   
        // displays its length.  
        Task<int> download1 =   
            ProcessURLAsync("http://msdn.microsoft.com", client);  
        Task<int> download2 =   
            ProcessURLAsync("http://msdn.microsoft.com/library/hh156528(VS.110).aspx", client);  
        Task<int> download3 =   
            ProcessURLAsync("http://msdn.microsoft.com/library/67w7t67f.aspx", client);  
  
        // Await each task.  
        int length1 = await download1;  
        int length2 = await download2;  
        int length3 = await download3;  
  
        int total = length1 + length2 + length3;  
  
        // Display the total count for the downloaded websites.  
        resultsTextBox.Text +=  
            string.Format("\r\n\r\nTotal bytes returned:  {0}\r\n", total);  
    }  
    ```  
  
5.  <span data-ttu-id="4ab24-142">F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-142">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="4ab24-143">프로그램을 여러 번 실행하여 세 가지 작업이 항상 동일한 순서로 완료되지는 않으며, 완료되는 순서가 생성 및 대기된 순서와 다를 수도 있음을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-143">Run the program several times to verify that the three tasks don’t always finish in the same order and that the order in which they finish isn't necessarily the order in which they’re created and awaited.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ab24-144">예</span><span class="sxs-lookup"><span data-stu-id="4ab24-144">Example</span></span>  
 <span data-ttu-id="4ab24-145">다음 코드에는 전체 예제가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ab24-145">The following code contains the full example.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Threading.Tasks;  
using System.Windows;  
using System.Windows.Controls;  
using System.Windows.Data;  
using System.Windows.Documents;  
using System.Windows.Input;  
using System.Windows.Media;  
using System.Windows.Media.Imaging;  
using System.Windows.Navigation;  
using System.Windows.Shapes;  
  
// Add the following using directive, and add a reference for System.Net.Http.  
using System.Net.Http;  
  
namespace AsyncExample_MultipleTasks  
{  
    public partial class MainWindow : Window  
    {  
        public MainWindow()  
        {  
            InitializeComponent();  
        }  
  
        private async void startButton_Click(object sender, RoutedEventArgs e)  
        {  
            resultsTextBox.Clear();  
            await CreateMultipleTasksAsync();  
            resultsTextBox.Text += "\r\n\r\nControl returned to startButton_Click.\r\n";  
        }  
  
        private async Task CreateMultipleTasksAsync()  
        {  
            // Declare an HttpClient object, and increase the buffer size. The  
            // default buffer size is 65,536.  
            HttpClient client =  
                new HttpClient() { MaxResponseContentBufferSize = 1000000 };  
  
            // Create and start the tasks. As each task finishes, DisplayResults   
            // displays its length.  
            Task<int> download1 =   
                ProcessURLAsync("http://msdn.microsoft.com", client);  
            Task<int> download2 =   
                ProcessURLAsync("http://msdn.microsoft.com/library/hh156528(VS.110).aspx", client);  
            Task<int> download3 =   
                ProcessURLAsync("http://msdn.microsoft.com/library/67w7t67f.aspx", client);  
  
            // Await each task.  
            int length1 = await download1;  
            int length2 = await download2;  
            int length3 = await download3;  
  
            int total = length1 + length2 + length3;  
  
            // Display the total count for the downloaded websites.  
            resultsTextBox.Text +=  
                string.Format("\r\n\r\nTotal bytes returned:  {0}\r\n", total);  
        }  
  
        async Task<int> ProcessURLAsync(string url, HttpClient client)  
        {  
            var byteArray = await client.GetByteArrayAsync(url);  
            DisplayResults(url, byteArray);  
            return byteArray.Length;  
        }  
  
        private void DisplayResults(string url, byte[] content)  
        {  
            // Display the length of each website. The string format   
            // is designed to be used with a monospaced font, such as  
            // Lucida Console or Global Monospace.  
            var bytes = content.Length;  
            // Strip off the "http://".  
            var displayURL = url.Replace("http://", "");  
            resultsTextBox.Text += string.Format("\n{0,-58} {1,8}", displayURL, bytes);  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ab24-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ab24-146">See Also</span></span>  
 [<span data-ttu-id="4ab24-147">연습: async 및 await를 사용하여 웹에 액세스(C#)</span><span class="sxs-lookup"><span data-stu-id="4ab24-147">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  
 [<span data-ttu-id="4ab24-148">async 및 await를 사용한 비동기 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="4ab24-148">Asynchronous Programming with async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/index.md)  
 [<span data-ttu-id="4ab24-149">방법: Task.WhenAll을 사용하여 비동기 연습 확장(C#)</span><span class="sxs-lookup"><span data-stu-id="4ab24-149">How to: Extend the async Walkthrough by Using Task.WhenAll (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
