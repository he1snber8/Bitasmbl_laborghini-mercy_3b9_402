# Quickstart for Bitasmbl project (.NET)

## 1) Install Bitasmbl-CLI package

```bash
npm i bitasmbl-cli
```

## 2) Run bitasmbl command to set up the project

```bash
bitasmbl pull --repoUrl https://github.com/he1snber8/Bitasmbl_laborghini-mercy_3b9_402 --appId 402 --repoId 225
```

## 3) Enter into the main directory and start coding!

```bash
cd Bitasmbl_laborghini-mercy_3b9_402
```

## Customize requirements in a way you like

Bitasmbl organizes development into requirements. Each requirement describes a feature or implementation goal and can define suggested file locations through a `paths` array.

The `paths` property acts as a mapping guideline, helping contributors understand where related code should live.

You can customize `paths` mappings through the `bitasmbl.json` file.

{"Requirement":"User Feedback Form UI","Paths":["**/src/features/feedback-form/**","**/src/components/inputs/**","**/src/styles/feedback-form/**"]}


## What you should do

### User Feedback Form UI

Create a responsive React form for users to submit feedback and ratings.

### Feedback Listing & Filtering UI

Implement React views to list feedback entries with basic filtering.

### User Onboarding & Info Banner

Provide a short intro banner and basic guidance to encourage 10 users to submit feedback.

### Feedback Submission API

Expose a .NET endpoint to create feedback submissions with validation.

### Feedback Storage & Retrieval

Persist feedback in the database and provide queries for admin review.

### Basic Usage Metrics

Track count of unique feedback users and submissions over the first month.



## Requirement Evaluation

Bitasmbl includes a requirement evaluation workflow that lets contributors select a task and submit work for validation.

Run:

```bash
bitasmbl evaluate
```

Example output:

<pre>
? Available Requirements:

❯ [<span style="color:#9333ea">1</span>] <span style="color:#9333ea"> Define portfolio layout </span>            [3]
  [2] Build showcase components            [3]
  [3] Implement navigation routing         [3]
</pre>

`[x]` on the right represents the number of submission attempts remaining for a requirement.

## Example evaluation result

```csharp
/*
|--------------------------------------------------------------------------
| BITASMBL EVALUATION
|--------------------------------------------------------------------------
| REQUIREMENT:
| Implement product catalog API
|
| SCORE: 12/100
| STATUS: FAIL ✕
|
| INSIGHT:
| The endpoint returns static product data and does not use a repository,
| service layer, filtering, or async database access.
|--------------------------------------------------------------------------
*/

using Microsoft.AspNetCore.Mvc;

namespace BitasmblProject.Features.Catalog;

[ApiController]
[Route("api/products")]
public sealed class ProductsController : ControllerBase
{
    [HttpGet]
    public IActionResult GetProducts()
    {
        var products = new[]
        {
            new { Id = 1, Name = "Keyboard", Price = 89.99 },
            new { Id = 2, Name = "Mouse", Price = 49.99 }
        };

        return Ok(products);
    }
}
```


## Final project evaluation 

final project info ui will display here

## Learn More

For complete command references, workflow explanations, and additional documentation, visit:

👉 [Bitasmbl Documentation](https://bitasmbl.com/docs)