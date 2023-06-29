+++
title = "Some post"
date = 2023-06-25
+++

Lorem ipsum dolor sit, amet consectetur adipisicing elit. Hic saepe, in ad similique, modi debitis id mollitia reiciendis totam nostrum sapiente vitae nulla eum, ex ab doloremque repudiandae atque aut ducimus possimus eaque. Corporis impedit earum, laudantium accusamus suscipit odio dolores neque. `Fugiat labore sit, eligendi ut`, quaerat laborum maiores et hic architecto quidem, aspernatur deleniti. 

Incidunt voluptate nam blanditiis repellendus aliquam optio quos dolores culpa deserunt, sint cupiditate suscipit non perferendis praesentium quidem, amet eaque, quam sequi dolore sed ipsum minima corporis veniam. Vel voluptatum sapiente quisquam ratione saepe officia aliquam animi exercitationem numquam reprehenderit. Architecto, distinctio? Libero, doloremque.


```rust
use std::error::Error;
use glob::glob;

fn main() -> Result<(), Box<dyn Error>> {
    for item in glob("**/*.txt")?{
        println!("{}", item?.display());
    }

    Ok(())
}
```

```sh
$ sudo apt install blender --full -y
```