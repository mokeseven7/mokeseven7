## Getting Started

```bash 

$ ./mike-mcgrath --help

NAME
     mike-mcgrath, mmcgrath
     
SYNOPSIS
     mike-mcgrath   [--title[=full-stack-engineer] [--experience=[=9 years]]

                    [--languages[=php,node,python,go] [--aws[=cloud practitioner]
                    
                    [--frameworks[=laravel, express, django, nest, mux]]
```

## 🔥🔥🔥

```php

namespace App\Http\Controllers;

use App\Http\Requests\{StoreCrudRequest,UpdateCrudRequest};

class CrudController extends Controller {

     public function store(StoreCrudRequest $request){
        return tap(Crud::create($request->safe()->all()), fn($crud) => response()->json($crud));
     }

     public function update(UpdateCrudRequest $request, Crud $crud){
        return tap($request->safe()->all(), fn($valid) => $crud->update($valid) && response()->json($crud->refresh()));
     }
}

```





