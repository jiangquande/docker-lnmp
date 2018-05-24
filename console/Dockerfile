FROM php:7.1-fpm

MAINTAINER jiangqd <505781913@qq.com>

 #安装 git curl vim zip
RUN apt-get update && apt-get install -y git curl vim libzip-dev libfreetype6-dev \
	&& rm -rf /var/lib/apt/list* \
    && docker-php-ext-install  zip

# 安装 composer
RUN curl -o composer.phar https://getcomposer.org/download/1.6.0/composer.phar \
	&& chmod +x composer.phar

# 配置 composer 包括引入中国国内镜像
RUN mv composer.phar /usr/local/bin/composer \
 	&& echo 'export PATH="$PATH:$HOME/.composer/vendor/bin"' >> ~/.bashrc \
 	&& . ~/.bashrc \
 	&& composer config -g repo.packagist composer https://packagist.phpcomposer.com

# 设置 Git 的身份
RUN git config --global user.name "jiangqd" \
	&& git config --global user.email "505781913@qq.com" \
	&& git config --global credential.helper store
