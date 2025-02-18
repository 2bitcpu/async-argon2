# async-argon2
Hashing and Verification with Argon2

## examples
```rust
#[tokio::main]
async fn main() -> Result<(), async_argon2::BoxError> {
    let password = String::from("password");

    let hash = async_argon2::hash(password.clone()).await?;
    println!("hash: {}", hash);

    let verified = async_argon2::verify(password, hash).await?;
    println!("verified: {}", verified);

    Ok(())
}
```