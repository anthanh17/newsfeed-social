# Define data model

![data model](./images/data-model.jpg)

SQL

```
CREATE TABLE "user" (
  "id" varchar PRIMARY KEY,
  "hash_password" varchar NOT NULL,
  "first_name" varchar,
  "last_name" varchar,
  "email" varchar NOT NULL,
  "user_name" varchar NOT NULL,
  "created_at" timestamptz NOT NULL DEFAULT (now()),
  "updated_at" timestamptz NOT NULL DEFAULT (now())
);

CREATE TABLE "user_user" (
  "fk_user_id" varchar NOT NULL,
  "fk_follow_id" varchar NOT NULL
);

CREATE TABLE "comment" (
  "id" varchar PRIMARY KEY,
  "fk_post_id" varchar NOT NULL,
  "fk_user_id" varchar NOT NULL,
  "content" text NOT NULL,
  "created_at" timestamptz NOT NULL DEFAULT (now()),
  "updated_at" timestamptz NOT NULL DEFAULT (now())
);

CREATE TABLE "post" (
  "id" varchar PRIMARY KEY,
  "fk_user_id" varchar NOT NULL,
  "content_text" text,
  "content_image_path" varchar NOT NULL,
  "visible" bool,
  "created_at" timestamptz NOT NULL DEFAULT (now()),
  "updated_at" timestamptz NOT NULL DEFAULT (now())
);

CREATE TABLE "like" (
  "fk_user_id" varchar,
  "fk_post_id" varchar NOT NULL,
  "created_at" timestamptz NOT NULL DEFAULT (now())
);

CREATE UNIQUE INDEX ON "user" ("user_name");

CREATE UNIQUE INDEX ON "like" ("fk_post_id", "fk_user_id");

ALTER TABLE "user_user" ADD FOREIGN KEY ("fk_user_id") REFERENCES "user" ("id");

ALTER TABLE "user_user" ADD FOREIGN KEY ("fk_follow_id") REFERENCES "user" ("id");

ALTER TABLE "comment" ADD FOREIGN KEY ("fk_post_id") REFERENCES "post" ("id");

ALTER TABLE "comment" ADD FOREIGN KEY ("fk_user_id") REFERENCES "user" ("id");

ALTER TABLE "post" ADD FOREIGN KEY ("fk_user_id") REFERENCES "user" ("id");

ALTER TABLE "like" ADD FOREIGN KEY ("fk_user_id") REFERENCES "user" ("id");

ALTER TABLE "like" ADD FOREIGN KEY ("fk_post_id") REFERENCES "post" ("id");

```
