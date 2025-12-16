# Start from a base image (e.g., Node.js as indicated by the npm command)
# You need to specify a relevant base image, for example:
FROM node:20-alpine

# Define the build-time argument and give it a default value if needed.
# The value "npm ci --omit=dev --frozen-lockfile" is the *command*
# you want to execute using the argument, not the argument's value itself.
# The argument name is NPM_BUILD.
ARG NPM_BUILD
# You can use the ARG in subsequent RUN instructions if it is redefined within the stage or used in the same scope.

# The `context: .` means the build context is the current directory from where you run 'docker build'.
# The `dockerfile: docker/Dockerfile` means the Dockerfile is located in the 'docker' directory.

# Set the working directory inside the container (optional, but good practice).
# WORKDIR /app

# Copy your application files into the image.
COPY . .

# Run the npm build command using the build argument's value.
# This assumes the base image is a Node.js image and the application is present.
# Since the argument itself is the command, we might need a different approach or assume the user runs the command.
# If the goal is to run a specific command, you might use it directly:

RUN npm ci --omit=dev --frozen-lockfile 

# Expose the port the container will listen on at runtime.
EXPOSE 8080

# Define the default command to run when the container starts (replace with your actual start command).

CMD ["node", "index.js"] 
