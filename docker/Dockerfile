# Stage 1: Build the React Application
FROM node:20-alpine AS build
WORKDIR /app

# Install dependencies
COPY package*.json ./
RUN npm install

# Copy source code and build
COPY . .
RUN npm run build

# Stage 2: Serve with Nginx (Production)
FROM nginx:alpine
WORKDIR /usr/share/nginx/html

# SRE: Healthcheck for automated rollback
HEALTHCHECK --interval=30s --timeout=10s --retries=3 \
  CMD curl -f http://localhost/ || exit 1

# Copy built assets from Stage 1
COPY --from=build /app/dist .

# Copy Nginx config (Path fixed relative to build context)
COPY nginx/frontend.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
