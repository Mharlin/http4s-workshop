Tobis presentation took about 25 minutes and then a couple of minutes to go through the exercise

19 minutes into lightweigh functional microservices with http4s and doobie he shows a very nice example of the
difference between future and IO.
Side effects? slice https://kubukoz.github.io/talks/http4s-doobie-micro/slides/

```
val x = Future(StdIn.readLine())

(x >> x) <!-> (Future(StdIn.readLine()) >> Future(StdIn.readLine()))
```
On the left side readLine will be run once and on the right hand side twice

```
val x = IO(StdIn.readLine())

(x >> x) <!-> (IO(StdIn.readLine()) >> Future(StdIn.readLine()))
```
In this case the readLine will be run twice on both sides because we have referencial transparency

To get .toJson and EntityEncoder that's needed http4s with http messages
```
import org.http4s.circe._
import io.circe.syntax._
```
