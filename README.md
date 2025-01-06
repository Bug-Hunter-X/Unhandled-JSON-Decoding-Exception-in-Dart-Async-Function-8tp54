# Unhandled JSON Decoding Exception in Dart

This repository demonstrates a common error in Dart applications: insufficient error handling when decoding JSON responses from asynchronous operations.  The `bug.dart` file contains code that fetches data from a hypothetical API.  If the API returns an error or non-JSON data, the application crashes. The solution, in `bugSolution.dart`, adds robust error handling.

## Problem

The `fetchData` function in `bug.dart` uses `jsonDecode` without checking for potential exceptions.  Network errors or unexpected responses can lead to a `FormatException` or other runtime errors, causing the app to crash.

## Solution

The `bugSolution.dart` file addresses this issue by adding comprehensive error handling: 

1.  **Checking the HTTP status code:**  It verifies `response.statusCode` to ensure the request was successful.
2.  **Try-catch block:** A `try-catch` statement handles potential exceptions during `jsonDecode` and network requests.
3.  **Specific Exception Handling:** The code can be extended to handle specific exceptions, such as `FormatException` for invalid JSON or `SocketException` for network issues.
4.  **Informative error messages:**  Clear error messages help in debugging and provide user feedback in production.