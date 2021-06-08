FROM node:alpine

WORKDIR '/app'

# Copy dependincies
COPY package.json .

# Install
RUN npm install

# Copy the rest
COPY . .

# Run application
RUN npm run build
# Start production server
FROM nginx
COPY --from=builder /app/build /user/share/nginx/html