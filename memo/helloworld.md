
# Console App

```csharp
using System;

public class HelloWorld
{
    static public void Main ()
    {
        Console.WriteLine ("Hello World!");
    }
}
```
```sh
$ mcs test.cs 
$ ./test.exe 
Hello World!
```

# HttpClient

```csharp
using System;
using System.Net.Http;
using System.Threading.Tasks;

namespace ConsoleApplication
{
    public class Program
    {
        public static void Main()
        {
            GetGoogle().GetAwaiter().GetResult();
        }
        public static async Task GetGoogle() 
        {
            using(var client = new HttpClient())
            {
                var result = await client.GetAsync("https://www.google.co.jp");
                Console.WriteLine(result.StatusCode);
            }
        }
    }
}
```
```sh
$ mcs /reference:System.Net.Http.dll http.cs 
$ ./http.exe 
```
https://docs.microsoft.com/ja-jp/aspnet/web-api/overview/advanced/calling-a-web-api-from-a-net-client#create-the-console-application

