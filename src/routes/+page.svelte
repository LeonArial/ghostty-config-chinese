<script lang="ts">
    import Page from "$lib/views/Page.svelte";
    import logo from "$lib/images/ghost.svg";
    import sync from "$lib/images/tabs/sync.webp";
    import fonts from "$lib/images/tabs/font-playground.webp";
    import Admonition from "$lib/components/Admonition.svelte";
    import Group from "$lib/components/settings/Group.svelte";
    import LinkItem from "$lib/components/settings/LinkItem.svelte";
    import Separator from "$lib/components/settings/Separator.svelte";
</script>

<Page title="Ghostty Config">
    <section>
        <div class="user">
            <div class="user-avatar">
                <img src={logo} alt="Ghostty Logo" />
            </div>
            <div class="user-label">
                <div class="user-name">Ghostty Config<sup>β</sup></div>
                <div class="user-subtext">社区工具</div>
            </div>
        </div>
        <Admonition>
            本工具仍处于 Beta 阶段，肯定会有 Bug！如果遇到问题，请在 GitHub 上
            <a
                href="https://github.com/zerebos/ghostty-config/issues"
                target="_blank"
                rel="noopener noreferrer">报告</a>
            。
        </Admonition>
        <Group>
            <LinkItem name="导入 & 导出" href="/app/import-export" icon={sync} />
            <Separator />
            <LinkItem name="字体预览" href="/app/font-playground" icon={fonts} />
        </Group>
        <Group title="更新日志 v0.1.1">
            <ul>
                <li>
                    添加了 Ghostty 中新增的配置选项（如 macOS 图标自定义）。
                </li>
                <li>更新了部分默认值以匹配 Ghostty 的最新默认值。</li>
                <li>调整了部分设置的顺序以优化结构。</li>
                <li>将描述从“非官方工具”改为“社区工具”。</li>
            </ul>
        </Group>
        <div class="group-wrapper">
            <Group title="路线图" flex={1}>
                <ul>
                    <li>快捷键验证</li>
                    <li>帮助文档</li>
                    <li>允许手动输入颜色值</li>
                    <li>导入/导出的单元测试</li>
                    <li>统一配色方案</li>
                    <li>重构与代码清理</li>
                    <li>macOS 图标预览</li>
                </ul>
            </Group>
            <Group title="潜在想法">
                <ul>
                    <li>自定义设置类型以更贴近 Ghostty 配置</li>
                    <li>添加重置单个设置的功能</li>
                    <li>将颜色选择器从模态框改为弹出式</li>
                    <li>详细的终端预览与演练场</li>
                </ul>
            </Group>
        </div>
    </section>
</Page>

<style>
    section {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        flex: 0.6;
    }

    .user {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 8px;
        margin: 20px 0;
    }

    .user-avatar img {
        height: 80%;
        width: 80%;
    }

    .user-avatar {
        display: inline-flex;
        justify-content: center;
        align-items: center;
        background: linear-gradient(#03028f, #09043a);
        height: 100px;
        width: 100px;
        border-radius: 50%;
        /* border: 2px solid black; */
        /* box-shadow: 0 0 0 2px white; */
    }

    .user-label {
        flex: 1;
        display: flex;
        flex-direction: column;
        justify-content: center;
        gap: 5px;
    }

    .user-name {
        position: relative;
        display: flex;
        justify-content: center;
        font-size: 1.3rem;
        color: var(--font-color);
        font-weight: 600;
    }

    sup {
        position: absolute;
        color: var(--font-color-accent);
        right: -11px;
        top: -5px;
    }

    .user-subtext {
        display: flex;
        justify-content: center;
        font-size: 1.1rem;
    }

    .group-wrapper {
        display: flex;
        width: 100%;
        gap: 12px;
    }

    ul,
    .group-wrapper ul {
        /* list-style: "↪ "; */
        list-style: "🠶 ";
        padding-left: 15px;
        margin: 0;
        display: flex;
        flex-direction: column;
        height: 100%;
        justify-content: space-evenly;
    }

    /* code {
        background: var(--bg-input-focus);
        padding: 2px 4px;
        border: 1px solid var(--border-input);
        border-radius: var(--radius-level-4);
    } */
</style>
