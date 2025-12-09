# C++ Notes - Nov. 06, 2025

## Three ways to pass an object

1. `Pass by copy`

   - No need of any symbol
   - The passed objet is copied

   ```
   void foo(Object x){
   }
   ```

2. `Pass by reference`

   - Use `&` for this
   - The actual object is passed, no copy
   - Not nullable, you can't pass a null object
   - You can modify the object, unless its const

   ```
   void foo(Object& x){
   }
   ```

3. `Pass by pointer`

   - Use `*` for this
   - The address of the object will be passed
   - Nullable
   - You can modify the object, unless its const

   ```
   void foo(Object* x){
   }
   ```
