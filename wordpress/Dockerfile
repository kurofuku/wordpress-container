FROM		php:fpm-buster

RUN			\
			# Update to latest
			apt -y update && \
			apt -y install default-mysql-client libmagickwand-dev && \
			pecl install apcu imagick && \
			echo "extension=apcu.so" > $PHP_INI_DIR/conf.d/apcu.ini && \
			docker-php-ext-install mysqli opcache bcmath && \
			docker-php-ext-enable mysqli opcache bcmath imagick && \
			# Copy customized configuraiton file
			cp /wordpress-temp/zz-docker.conf /usr/local/etc/php-fpm.d/zz-docker.conf && \
			# Done
			echo "Build complete."
