# syntax=docker/dockerfile:1

# Base stage
FROM php:8.3-fpm AS base

RUN apt-get update && apt-get install -y \
    curl \
    unzip \
    libpq-dev \
    libonig-dev \
    libssl-dev \
    libxml2-dev \
    libcurl4-openssl-dev \
    libicu-dev \
    libzip-dev \
    && docker-php-ext-install -j$(nproc) \
    pdo_mysql \
    pdo_pgsql \
    pgsql \
    opcache \
    intl \
    zip \
    bcmath \
    soap \
    && pecl install redis xdebug \
    && docker-php-ext-enable redis xdebug

# Development stage
FROM base AS development

# Aqui você pode adicionar comandos específicos para o ambiente de desenvolvimento
# Por exemplo, instalar ferramentas de desenvolvimento adicionais

# Production stage (opcional)
# FROM base AS production
# Aqui você pode adicionar comandos específicos para o ambiente de produção
