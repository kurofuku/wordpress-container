FROM		php:fpm-buster

RUN			\
			# Update to latest
			apt -y update && \
			apt -y install default-mysql-client && \
			docker-php-ext-install mysqli opcache bcmath && \
			pecl install apcu && \
			echo "extension=apcu.so" > $PHP_INI_DIR/conf.d/apcu.ini && \
			# Done
			echo "Build complete."
