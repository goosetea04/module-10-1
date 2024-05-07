## Reflection 1.2

After we add `println!("Gusti's Computer: hey hey");`, when we run, we come to find out that this message gets printed out first, even though it appears after the spawner we spawned. Inn rust, when we spawn a task using `spawner.spawn`, it gets added to the ready queue. Then, the executor picks it up from the queue and starts executing it when the resources are available. 

In our `main.rs` file, we print "Gusti's Computer: hey hey" before dropping the spawner and running the executor. Since the executor hasn't started executing the spawned task yet, the "hey hey" message gets printed first.