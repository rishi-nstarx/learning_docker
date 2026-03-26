# First stage.
FROM node:22-alpine AS build
WORKDIR /app
COPY package*.json .
RUN npm ci

COPY src src
COPY tsconfig.json tsconfig.json

# this will make 'dist' directory available inside  stage 'build'.
# 'npm run build' generates JS from TS.
RUN npm run build



# Second stage.
FROM node:22-alpine AS deps
WORKDIR /app
COPY package*.json .
RUN npm ci --only=production



# Final stage.
# Using distroless image.
FROM gcr.io/distroless/nodejs22
WORKDIR /app

# As we want only production level dependencies to optimize image.
COPY --from=deps /app/node_modules node_modules

# Referenecing the stage 'build' as previous stage and copying resources from there.
# COPY --from=build /app/node_modules node_modules
COPY --from=build /app/dist dist

ENV PORT=300

CMD ["dist/index.js"]
