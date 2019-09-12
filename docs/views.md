---
id: views
title: Views
sidebar_label: Views
---

## Introduction to views

The view in Runcinator are make with Laravel Blade templates.
[Visit official documentation from view](https://laravel.com/docs/5.8/blade)

### Using if
To make conditions with blade template:

```
@if(true)
    <p>Always here</p>
@else
    <p>Never here</p>
@endif
```

### Using while
To make while loop with blade template:

```
@while(true)
    <p>Wow! Its a infinite loooooooooooooop!</p>
@endwhile
```

### Using for
To make for loop with blade template:

```
<ul>
@for( $i = 0; $i < 10; $i++ )
    <li>
        Item {{ $i }}
    </li>
@endfor
</ul>
```

### Using foreach
To make foreach loop with blade template:

```
<ul>
@foreach( $items as $item )
    <li>
        Item {{ $item->title }}
    </li>
@endforeach
</ul>
```

### Using forelse
To make forelse loop with blade template:

```
<ul>
@forelse( $items as $item )
    <li>
        Item {{ $item->title }}
    </li>
@empty
    <p>It's empty :(</p>
@endforelse
</ul>
```