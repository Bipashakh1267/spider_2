# Use the base image with Rust installed (e.g., rust:latest)
FROM rust:latest

# Set the working directory inside the container
WORKDIR /app

# Install system dependencies
RUN apt-get update && apt-get install -y libpq-dev

# Copy the backend application files into the container
COPY . .

# Build your application (modify as needed)
RUN cargo build

# Set environment variables for the database connection
ENV DATABASE_URL=postgres://spider2:2706@postgres/rust_server

# Install diesel_cli
RUN cargo install diesel_cli --no-default-features --features postgres

# Example: Run diesel setup and your application
CMD ["sh", "-c", "diesel setup --database-url $DATABASE_URL && cargo run"]
