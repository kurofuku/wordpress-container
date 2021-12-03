FROM		php:fpm-buster

RUN			\
			# Update to latest
			apt -y update && \
			apt -y install default-mysql-client libmagickwand-dev && \
			pecl install apcu imagick && \
			echo "extension=apcu.so" > $PHP_INI_DIR/conf.d/apcu.ini && \
			docker-php-ext-install mysqli opcache bcmath && \
			docker-php-ext-enable mysqli opcache bcmath imagick && \
			echo "post_max_size=128M" >  $PHP_INI_DIR/conf.d/upload_size.ini && \
			echo "upload_max_filesize=128M" >> $PHP_INI_DIR/conf.d/upload_size.ini && \
			# Done
			echo "Build complete."
